<template>
    <li>
        <div class="profile-card">
            <header class="profile-header">
                <img :src='dino.image'/>
                <h2>{{dino.name}}</h2>
            </header>
                <skillList v-show="dino.show" :skills='dino.skills'/>
        </div>
    </li>
</template>

<script>
import skillList from './skillList.vue'
export default {
    name: 'profiles',
    props: ['dino'],
    components: {
        skillList
    }
}
</script>

