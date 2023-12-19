<script >
import cardsList from './cardsList.vue';
export default{
    name: 'appMain',
    components: {
        cardsList
    }
}
</script>

<template>
   <main>
        <cardsList/>
   </main>
</template> 

<style lang="scss" scoped>
 @use '../style/general.scss' as *;
 @use '../style/partials/variables' as *; 

    main{
        background-color: $bg-brown;
        padding: 4rem;
    }

    
</style>