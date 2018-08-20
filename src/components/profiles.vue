<template>
    <section id="profiles-container">
        <h2>Profiles</h2>
        <ul id="profiles">
            <li v-on:click="shouldShow(dino)" v-for="dino in dinos" :key="dino.id">
                <div class="profile-card">
                    <header class="profile-header">
                    <img :src='dino.image' />
                    <h2>{{dino.name}}</h2>
                    </header>
                    <skillList v-show="dino.show" :skills='dino.skills' />
                </div>
            </li>
        </ul>
    </section>
</template>

<script>
import skillList from './skillList.vue'
export default {
    name: 'profiles',
    components: {
        skillList
    },
    data(){
        return {
            dinos: []
        }
    },
    mounted(){
    fetch('../../static/dinosaurs.json')
        .then(result => result.json())
        .then(results => {
            console.log(results)
            for (const obj of results) {
                obj.id = this.id
                obj.show = false
                this.id++
                this.dinos.push(obj)
            }
        })
    },
    methods: {
        shouldShow (dino) {
            console.log('hello')
            dino.show = !dino.show
        }
    }
}
</script>

