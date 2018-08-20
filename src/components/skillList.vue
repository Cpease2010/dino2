<template>
    <section class="skills-container" id='hidden'>
        <h4>Skills</h4>
        <ul class="skills-list">
            <li v-for="skill in skills" :key="skill">{{ skill }}</li>
        </ul>
    </section>
</template>

<script>
export default {
    name: 'skillList',
    props: ['skills'],
    data(){
        return {
            
        }
    },
    methods: {
        toggle: function () {
            document.querySelector('#hidden')
            return 
        }
    }
}
</script>

