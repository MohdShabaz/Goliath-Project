<template>

    <div class="Hello">
    
        <h1>IDEAS</h1>

        <form v-on:submit="addIdea">

            <input type="text" v-model="newIdea.note" placeholder="Start your idea!!!">
            <br />
            <input type="submit" value="Submit">

        </form>

        <ul>
            <li v-for="idea in ideas"> 
                    {{idea.note}} <button v-on:click="deleteIdea(idea)">x</button>
            </li>
        </ul>

    </div>

</template>

<script>
    export default{
        name: 'ideas',

        data() { 
            return {
                newIdea: {},
                ideas: [   /*
                    {
                    note:'Type Here'
                    }  */
                ]   
            }
        },
        methods: {
            addIdea: function(e){
                this.ideas.push({
                    note: this.newIdea.note,
                }); 
                this.newIdea = {};
                e.preventDefault();
            },
            deleteIdea: function(idea){
                this.ideas.splice(this.ideas.indexOf(idea),1);
            }
        },
    }
</script>   


<style scoped>

</style>
