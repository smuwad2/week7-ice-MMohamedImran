<script>
    import ViewPosts from './ViewPosts.vue';
    import axios from 'axios';

    export default { 

       // add code here
        components:{ViewPosts},

       data(){

   

        return{
            moods:['Happy','Sad','Angry'],
            subject:'',
            entry:'',
            selMood:'',
            outputMsg:'',
            
        }
       },
    computed: {
        baseUrl() {
            if (window.location.hostname=='localhost')
                return 'http://localhost:3000' 
            else {
                const codespace_host = window.location.hostname.replace('5173', '3000')
                return `https://${codespace_host}`;
            }
        }
    },
    methods:{
        addPost(){
            axios.get(`${this.baseUrl}/updatePost`,
                {
                    params:{
                        subject:this.subject,
                        entry:this.entry,
                        mood:this.selMood,

                    }
                }
            )
            .then(response=>{
                this.outputMsg=response.data.message;
            })
            .catch(error=>{
                console.log(error)
            })
        }
    }

    }
</script>

<template>
    <ViewPosts />
</template>