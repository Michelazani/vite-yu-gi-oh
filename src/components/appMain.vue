<script >
import cardsList from './cardsList.vue';
import {store} from '../js/store.js';
export default{
    name: 'appMain',
    components: {
        cardsList
    },
    data(){
        return{
            store
        }
    }
}
</script>

<template>
   <main>
        <select name="archetype_nanme" id="archetype_name">
            <option value="">Alien</option>
            <option value="">others</option>
        </select>
        <cardsList/>
   </main>
</template> 

<style lang="scss" scoped>
 @use '../style/general.scss' as *;
 @use '../style/partials/variables' as *; 

    main{
        background-color: $bg-brown;
        padding: 4rem;
        select{
            margin: 0 0 3rem 2rem;
        }
    }
</style>