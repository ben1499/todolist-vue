<template>
    <div id="search">
        <input @keyup.enter="submitTodo" v-model="input" type="text" placeholder="Type here">
        <button @click="submitTodo">+</button>
    </div>
  </template>
  
  <script>

  
  export default {
    data() {
       return {
            input: '',
       }
    },
    components: {
      
    },
    methods: {
        submitTodo: function() {
            if (this.input) {
                this.$emit('item-submitted', this.input)
                this.input = '';
            }
            
        }
    }
  }
  </script>
  
  <style scoped>
    #search {
        display: flex;
        justify-content: center;
        gap: 20px;
        min-height: 40px;
        width: 100%;
        position: relative;
        margin-bottom: 5px;
    }

    input[type='text'] {
        width: 93%;
        border: 1.5px solid #068FFF;
        border-radius: 8px;
        padding: 10px 5px;

    }

    input[type='text']:focus {
        border: none;
        outline: none;
        border: 1.9px solid #4E4FEB;

    }

    input[type='text']:focus-visible {
        border: none;
        outline: none;
        border: 1.9px solid #4E4FEB;
        
    }

    button {
        border: none;
        border-radius: 8px;
        width: 50px;
        height: 100%;
        background: #4E4FEB;
        color: #fff;
        font-size: 23px;
        position: absolute;
        right: 12px;
    }

    button:hover {
        background: #068FFF;
    }
  </style>
  