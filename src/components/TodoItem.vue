<template>
    <div id="todo">
        <ul>
            <li v-for="(item,index) in items" :key="index">{{ item }} 
                <button v-bind:data-item="index" @click="removeItem"><i class="fa-solid fa-check"></i></button>
            </li>
        </ul>
    </div>
</template>
<script>

  
export default {
    props: ['items'],
    data() {
       return {
       }
    },
    components: {
      
    },
    methods: {
        removeItem(e) {
            const element = e.currentTarget;
            const elementPosition = element.getAttribute('data-item');
            this.$emit('item-removed', elementPosition);
            // this.items.splice(elementPosition, 1);
        }
    }
}
</script>
   
<style scoped>
button {
    border: none;
    border: 1px solid #000;
    border-radius: 5px;
    width: 30px;
    height: auto;
}


button:hover {
    opacity: 0.5;
}

ul {
    margin: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 0;
    padding: 10px 10px; 
}


li {
    background-color: #eee;
    margin-bottom: 5px;
    list-style-type: none;
    display: flex;
    justify-content: space-between;
    padding: 15px 10px;
    border-radius: 6px;
    font-size: 0.9rem;
}
</style>
  