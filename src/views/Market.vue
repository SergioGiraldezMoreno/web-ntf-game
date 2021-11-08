<template>
    <!-- TODO: SEARCH ENGINE, TO LOOK FOR SKILLS BY ITS NAME-->
    <div class="m-0 min-vh-100 bg-dark pb-2">
        <div id="filter-div" class="position-fixed text-white text-center ps-3 pe-2 pe-md-3 rounded-bottom">
            <div v-if="showFilter" class="d-flex py-2 pt-md-3 ">
                <div class="border-end pe-1">
                    <button @click="revertFilter('blood')" class="filter-button">
                        <img :class="{disabled_filter: shouldBeDisabled('blood')}" class="filter-panel-icon" src="../assets/blood-icon.png" alt="">
                    </button>
                    <button @click="revertFilter('holy')" class="filter-button">
                        <img :class="{disabled_filter: shouldBeDisabled('holy')}" class="filter-panel-icon" src="../assets/holy-icon.png" alt="">
                    </button>
                    <button @click="revertFilter('venom')" class="filter-button">
                        <img :class="{disabled_filter: shouldBeDisabled('venom')}" class="filter-panel-icon" src="../assets/venom-icon.png" alt="">
                    </button>
                    <button @click="revertFilter('shadow')" class="filter-button">
                        <img :class="{disabled_filter: shouldBeDisabled('shadow')}" class="filter-panel-icon" src="../assets/shadow-icon.png" alt="">
                    </button>
                </div>
                <div class="px-1">
                    <button @click="revertFilter('attack')" class="filter-button">
                        <img :class="{disabled_filter: shouldBeDisabled('attack')}" class="filter-panel-icon" src="../assets/attack-icon.png" alt="">
                    </button>
                    <button @click="revertFilter('defense')" class="filter-button">
                        <img :class="{disabled_filter: shouldBeDisabled('defense')}" class="filter-panel-icon" src="../assets/defense-icon.png" alt="">
                    </button>
                    <button @click="revertFilter('heal')" class="filter-button">
                        <img :class="{disabled_filter: shouldBeDisabled('heal')}" class="filter-panel-icon" src="../assets/heal-icon.png" alt="">
                    </button>
                </div>
                <div class="border-start border-end px-1">
                    <button @click="revertFilter('copper')" class="filter-button">
                        <img :class="{disabled_filter: shouldBeDisabled('copper')}" class="filter-panel-icon" src="../assets/copper-icon.png" alt="">
                    </button>
                    <button @click="revertFilter('silver')" class="filter-button">
                        <img :class="{disabled_filter: shouldBeDisabled('silver')}" class="filter-panel-icon" src="../assets/silver-icon.png" alt="">
                    </button>
                    <button @click="revertFilter('gold')" class="filter-button">
                        <img :class="{disabled_filter: shouldBeDisabled('gold')}" class="filter-panel-icon" src="../assets/gold-icon.png" alt="">
                    </button>
                    <button @click="revertFilter('ruby')" class="filter-button">
                        <img :class="{disabled_filter: shouldBeDisabled('ruby')}" class="filter-panel-icon" src="../assets/ruby-icon.png" alt="">
                    </button>
                    <button @click="revertFilter('obsidiana')" class="filter-button">
                        <img :class="{disabled_filter: shouldBeDisabled('obsidiana')}" class="filter-panel-icon" src="../assets/obsidiana-icon.png" alt="">
                    </button>
                </div>
                <button @click="resetFilters()" class="p-0 m-0 ms-1 filter-button">
                    <img id="hide-filter-img" class="small-filter-icon" src="../assets/reset_icon.png" alt="">
                </button>
                <button @click="showFilter = false" class="p-0 m-0 filter-button">
                    <img id="hide-filter-img" class="small-filter-icon" src="../assets/hide-up-arrow.png" alt="">
                </button>
            </div>
            <div v-if="!showFilter" class="d-flex py-1">
                <p class="col my-auto">Filters</p>
                <button @click="showFilter = true" class="p-0 m-0 filter-button">
                    <img id="hide-filter-img" class="small-filter-icon" src="../assets/show-down-arrow.png" alt="">
                </button>
            </div>
        </div>
        <div class="container pb-3">
            <div id="card-container" class="container">
                <!-- TODO: MAYBE FOR THE MOBILE VERSION DO A INFINITE SCROLL OR A "CAROUSEL?" -->
                <div class="row justify-content-center">
                    <MarketPlaceCard class="col" v-for="skill in getFilteredSkillsByRow(0)" :key="skill.id" :skill="skill" />
                </div>
                <div class="row justify-content-center">
                    <MarketPlaceCard class="col" v-for="skill in getFilteredSkillsByRow(1)" :key="skill.id" :skill="skill" />
                </div>
            </div>
        </div>
        <div id="pages-carousel" class="w-100">
            <div class="justify-content-center d-flex">
                <button @click="previousPage" class="p-0">
                    <img class="p-2" src="../assets/sharp-arrow-left.png"/>
                </button>
                <button v-for="number in numberOfVisiblePages" @click="currentPage=number" :key="number" :disabled="currentPage == number">
                    {{number}}
                </button>
                <button @click="nextPage" class="p-0">
                    <img class="p-2" src="../assets/sharp-arrow-right.png"/>
                </button>
            </div>
            <p class="text-center text-white">Total pages: {{numberOfPages}}</p>
        </div>
    </div>
</template>

<script>
import MarketPlaceCard from "../components/MarketPlaceCard.vue";

export default {
    name: 'Market',
    components: {
        MarketPlaceCard,
    },
    data() {
        return {
            showFilter: false,
            currentPage: 1,
            skillsPerPage: 10,
            numberOfPages: 1,
            filters: [{id: 1, name: "venom", group: "attribute", img: "../assets/venom-icon.png", active: false},
                {id: 2, name: "holy", group: "attribute", img: "../assets/holy-icon.png", active: false},
                {id: 3, name: "shadow", group: "attribute", img: "../assets/shadow-icon.png", active: false},
                {id: 4, name: "blood", group: "attribute", img: "../assets/blood-icon.png", active: false},
                {id: 5, name: "attack", group: "type", img: "../assets/attack-icon.png", active: false},
                {id: 6, name: "defense", group: "type", img: "../assets/defense-icon.png", active: false},
                {id: 7, name: "heal", group: "type", img: "../assets/heal-icon.png", active: false},
                {id: 8, name: "copper", group: "tier", img: "../assets/copper-icon.png", active: false},
                {id: 9, name: "silver", group: "tier", img: "../assets/silver-icon.png", active: false},
                {id: 10, name: "gold", group: "tier", img: "../assets/gold-icon.png", active: false},
                {id: 11, name: "ruby", group: "tier", img: "../assets/ruby-icon.png", active: false},
                {id: 12, name: "obsidiana", group: "tier", img: "../assets/obsidiana-icon.png", active: false}],
            skills: []
        }
    },
    mounted() {
        this.loadSkillsData()
        window.addEventListener('resize', this.updatePagesData);
    },
    unmounted() {
        window.removeEventListener('resize', this.updatePagesData);
    },
    computed :{
        numberOfVisiblePages() {
            if (this.numberOfPages <= 3) {
                return this.numberOfPages
            }
            if (this.currentPage == 1) {
                return [1,2,3]
            } else if (this.currentPage == this.numberOfPages){
                return [this.currentPage-2, this.currentPage-1,this.currentPage]
            } else {
                return [this.currentPage-1, this.currentPage, this.currentPage+1]
            }
        }
    },
    methods: {
        loadSkillsData() {
            // this will be a call to an API or a DB the skills may have more info
            var skillsLoaded = [{id: 1, name: "Skill 1", attribute: "venom", type: "defense", tier: "copper", img: "assets/marco_holy_copper.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 2, name: "Skill 2", attribute: "venom", type: "attack", tier: "gold", img: "assets/marco_blood_gold.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 3, name: "Skill 3", attribute: "shadow", type: "defense", tier: "copper", img: "assets/marco_holy_copper.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 4, name: "Skill 4", attribute: "holy", type: "attack", tier: "obsidiana", img: "assets/marco_holy_obsidiana.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 5, name: "Skill 5", attribute: "venom", type: "heal", tier: "gold", img: "assets/marco_blood_gold.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 6, name: "Skill 6", attribute: "holy", type: "defense", tier: "copper", img: "assets/marco_holy_copper.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 7, name: "Skill 7", attribute: "blood", type: "defense", tier: "gold", img: "assets/marco_blood_gold.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 8, name: "Skill 8", attribute: "venom", type: "attack", tier: "copper", img: "assets/marco_holy_copper.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 9, name: "Skill 9", attribute: "shadow", type: "defense", tier: "copper", img: "assets/marco_holy_copper.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 10, name: "Skill 10", attribute: "shadow", type: "attack", tier: "obsidiana", img: "assets/marco_shadow_obsidiana.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 11, name: "Skill 11", attribute: "holy", type: "attack", tier: "silver", img: "assets/marco_venom_silver.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 12, name: "Skill 12", attribute: "blood", type: "heal", tier: "silver", img: "assets/marco_venom_silver.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 13, name: "Skill 13", attribute: "venom", type: "attack", tier: "silver", img: "assets/marco_venom_silver.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 14, name: "Skill 14", attribute: "blood", type: "defense", tier: "copper", img: "assets/marco_holy_copper.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 15, name: "Skill 15", attribute: "venom", type: "defense", tier: "gold", img: "assets/marco_blood_gold.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 16, name: "Skill 16", attribute: "shadow", type: "heal", tier: "gold", img: "assets/marco_blood_gold.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 17, name: "Skill 17", attribute: "shadow", type: "attack", tier: "gold", img: "assets/marco_blood_gold.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 18, name: "Skill 18", attribute: "holy", type: "defense", tier: "copper", img: "assets/marco_holy_copper.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 19, name: "Skill 19", attribute: "holy", type: "attack", tier: "ruby", img: "assets/marco_holy_ruby.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 20, name: "Skill 20", attribute: "venom", type: "heal", tier: "ruby", img: "assets/marco_holy_ruby.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 21, name: "Skill 21", attribute: "blood", type: "heal", tier: "copper", img: "assets/marco_holy_copper.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 22, name: "Skill 22", attribute: "venom", type: "defense", tier: "copper", img: "assets/marco_holy_copper.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 23, name: "Skill 23", attribute: "holy", type: "attack", tier: "copper", img: "assets/marco_holy_copper.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 24, name: "Skill 24", attribute: "blood", type: "attack", tier: "silver", img: "assets/marco_venom_silver.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 25, name: "Skill 25", attribute: "venom", type: "attack", tier: "silver", img: "assets/marco_venom_silver.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 26, name: "Skill 26", attribute: "blood", type: "defense", tier: "ruby", img: "assets/marco_holy_ruby.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 28, name: "Poisonous punch", attribute: "venom", type: "attack", tier: "ruby", img: "assets/SKILLS/ataqueserpiente_rubi.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 29, name: "Poisonous punch", attribute: "venom", type: "attack", tier: "silver", img: "assets/SKILLS/ataqueserpiente_silver.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 30, name: "Poisonous punch", attribute: "venom", type: "attack", tier: "copper", img: "assets/SKILLS/ataqueserpiente_copper.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 31, name: "Poisonous punch", attribute: "venom", type: "attack", tier: "gold", img: "assets/SKILLS/ataqueserpiente_gold.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 32, name: "Poisonous punch", attribute: "venom", type: "attack", tier: "obsidiana", img: "assets/SKILLS/ataqueserpiente_obsidiana.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 35, name: "Lethal poison", attribute: "venom", type: "attack", tier: "gold", img: "assets/SKILLS/pocionmortal_gold.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 34, name: "Lethal poison", attribute: "venom", type: "attack", tier: "silver", img: "assets/SKILLS/pocionmortal_silver.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 33, name: "Lethal poison", attribute: "venom", type: "attack", tier: "copper", img: "assets/SKILLS/pocionmortal_copper.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 37, name: "Lethal poison", attribute: "venom", type: "attack", tier: "obsidiana", img: "assets/SKILLS/pocionmortal_obsidiana.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 43, name: "Lethal poison", attribute: "venom", type: "attack", tier: "obsidiana", img: "assets/SKILLS/pocionmortal_obsidiana_2.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 36, name: "Lethal poison", attribute: "venom", type: "attack", tier: "ruby", img: "assets/SKILLS/pocionmortal_rubi.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 41, name: "Vigorous venom", attribute: "venom", type: "defense", tier: "ruby", img: "assets/SKILLS/frascodeveneno_rubi.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 40, name: "Vigorous venom", attribute: "venom", type: "defense", tier: "gold", img: "assets/SKILLS/frascodeveneno_gold.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 38, name: "Vigorous venom", attribute: "venom", type: "defense", tier: "copper", img: "assets/SKILLS/frascodeveneno_copper.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 39, name: "Vigorous venom", attribute: "venom", type: "defense", tier: "silver", img: "assets/SKILLS/frascodeveneno_silver.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 42, name: "Vigorous venom", attribute: "venom", type: "defense", tier: "obsidiana", img: "assets/SKILLS/frascodeveneno_obsidiana.png", description: "Detail one of the Skill Detail two of the Skill"},
                {id: 27, name: "Skill 27", attribute: "blood", type: "heal", tier: "obsidiana", img: "assets/marco_blood_obsidiana.png", description: "Detail one of the Skill Detail two of the Skill"}]

            this.skills = skillsLoaded
            this.updatePagesData()
        },
        updatePagesData() {
            this.updateSkillsPerPage();
            this.updateNumberOfPages();
        },
        updateSkillsPerPage(){
            var width = window.innerWidth
            if (width > 1399) {
                this.skillsPerPage = 10;
            } else if (width > 991) {
                this.skillsPerPage = 8;
            } else if (width > 767) {
                this.skillsPerPage = 6;
            } else if (width > 575) {
                this.skillsPerPage = 4;
            } else {
                this.skillsPerPage = 2;
            }
        },
        updateNumberOfPages(){
            var currentListOfSkills = this.getFilteredSkills();
            var numPages = (currentListOfSkills.length / this.skillsPerPage);
            if (numPages % 1 == 0) {
                this.numberOfPages = numPages
            } else {
                this.numberOfPages = parseInt(numPages) + 1
            }
            if (this.currentPage > this.numberOfPages) {
                this.currentPage = this.numberOfPages
            } else if (this.currentPage == 0 && this.numberOfPages != 0) {
                this.currentPage = 1
            }
        },
        previousPage(){
            if (this.currentPage > 1){
                this.currentPage -= 1
            }
        },
        nextPage(){
            if (this.currentPage < this.numberOfPages){
                this.currentPage += 1
            }
        },
        getFilteredSkills() {
            var finalSkillsList = this.skills;
            finalSkillsList = this.filterByAttribute(finalSkillsList);
            finalSkillsList = this.filterByType(finalSkillsList);
            finalSkillsList = this.filterByTier(finalSkillsList);
            return finalSkillsList
        },
        getFilteredSkillsByRow(row) {
            var finalSkillsList = this.getFilteredSkills()
            var firstSkillIdx = (this.currentPage - 1) * this.skillsPerPage + (this.skillsPerPage / 2) * row
            var lastSkillIdx = firstSkillIdx + (this.skillsPerPage/2)
            var finalSkillsListRange = finalSkillsList.slice(firstSkillIdx, lastSkillIdx)
            return finalSkillsListRange
        },
        filterByAttribute(skills) {
            var filters = [];
            for (let filter in this.filters){
                if (this.filters[filter].group == "attribute") {
                    filters.push(this.filters[filter])
                }
            }
            if (this.isAnyFilterActive(filters)) {
                var validSkills = [];
                var validAttributes = [];
                var activeFilters = this.getActiveFilters(filters)
                for (let filterId in activeFilters) {
                    validAttributes.push(activeFilters[filterId].name);
                }
                for (let skillId in skills) {
                    if (validAttributes.includes(skills[skillId].attribute)) {
                        validSkills.push(skills[skillId]);
                    }
                }
                return validSkills
            }
            return skills
        },
        filterByType(skills) {
            var filters = [];
            for (let filter in this.filters){
                if (this.filters[filter].group == "type") {
                    filters.push(this.filters[filter])
                }
            }
            if (this.isAnyFilterActive(filters)) {
                var validSkills = [];
                var validTypes = [];
                var activeFilters = this.getActiveFilters(filters)
                for (let filterId in activeFilters) {
                    validTypes.push(activeFilters[filterId].name);
                }
                for (let skillId in skills) {
                    if (validTypes.includes(skills[skillId].type)) {
                        validSkills.push(skills[skillId]);
                    }
                }
                return validSkills
            }
            return skills
        },
        filterByTier(skills) {
            var filters = [];
            for (let filter in this.filters){
                if (this.filters[filter].group == "tier") {
                    filters.push(this.filters[filter])
                }
            }
            if (this.isAnyFilterActive(filters)) {
                var validSkills = [];
                var validTiers = [];
                var activeFilters = this.getActiveFilters(filters)
                for (let filterId in activeFilters) {
                    validTiers.push(activeFilters[filterId].name);
                }
                for (let skillId in skills) {
                    if (validTiers.includes(skills[skillId].tier)) {
                        validSkills.push(skills[skillId]);
                    }
                }
                return validSkills
            }
            return skills
        },
        isAnyFilterActive(filters) {
            var filtered = this.getActiveFilters(filters);
            return filtered.length > 0
        },
        getActiveFilters(filters) {
            var activeFilters = [];
            for (var i = 0; i < filters.length; i++) {
                if (filters[i].active){
                    activeFilters.push(filters[i])
                }
            }
            return activeFilters
        },
        revertFilter(filterName) {
            for (let filterId in this.filters) {
                if (this.filters[filterId].name == filterName) {
                    this.filters[filterId].active = !this.filters[filterId].active
                }
            }
            this.updateNumberOfPages();
        },
        shouldBeDisabled(filterName) {
            for (let filterId in this.filters) {
                var filter = this.filters[filterId]
                if (filter.name == filterName) {
                    var activeRelatedFilters = [];
                    for (let filterRelatedId in this.filters){
                        var relatedFilter = this.filters[filterRelatedId]
                        if ((relatedFilter.name != filter.name) & (relatedFilter.group == filter.group) & relatedFilter.active) {
                            activeRelatedFilters.push(relatedFilter)
                        }
                    }
                    if (activeRelatedFilters.length > 0){ 
                        return !this.filters[filterId].active
                    }
                    return false
                }
            }
        },
        resetFilters() {
            for (let filterId in this.filters) {
                this.filters[filterId].active = false
            }
            this.updateNumberOfPages();
        }
    }
}
</script>

<style scoped>

.disabled_filter {
    -webkit-filter: grayscale(100%);
    -moz-filter: grayscale(100%);
    -ms-filter: grayscale(100%);
    -o-filter: grayscale(100%);
    filter: grayscale(100%);
    filter: gray;
}

.disabled_filter:hover {
    -webkit-filter: none;
    -moz-filter: none;
    -ms-filter: none;
    -o-filter: none;
    filter: none;
    filter: none;
    filter: none;
}


.filter-button {
    width: auto;
    height: auto;
    padding: 0px;
    border: 0px;
    background-color: rgba(0, 0, 0, 0);
}
.filter-subdiv {
    border-right: solid 2px white;
}
.filter-panel-icon{
    margin: 2px;
    width: 40px;
}
.white-border-button{
    background-color: rgba(255, 255, 255, 0);
    border: 1px solid white;
    border-radius: 5px;
}
.small-filter-icon {
    width: 40px;
    padding: 10px;
}
.filter-button {
    background-color: rgba(255, 255, 255, 0);
    border: 0px;
}
#hide-filter-img {
    width: 40px;
}
#card-container {
    margin-top: 100px;
}
#filter-div{
    background-color: rgba(0, 0, 0, 0.7);
    left: 50%;
    transform: translateX(-50%);
    border-radius: 0 0 20px 20px;
    padding: 0px;
    z-index: 1;
}
#pages-carousel button{
    color: rgb(10, 10, 10);
    background-image: linear-gradient(to right, rgb(121, 92, 0), rgb(196, 150, 0) 98%);
    border: 1px solid black;
    min-width: 30px;
    max-width: 45px;
    max-height: 45px;
}
#pages-carousel button:disabled{
    background-image: linear-gradient(to right, rgba(87, 80, 58, 0.8), rgba(78, 70, 43, 0.8) 98%);
}
#pages-carousel img{
    height: 100%;
    width: auto;
}
@media screen and (max-width: 767px) {
    #filter-div{
        background-color: rgba(0, 0, 0, 0.7);
        border-radius: 0px;
        padding: 0px;
    } 
}
</style>