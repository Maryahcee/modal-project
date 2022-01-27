<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{sale: theme === 'sale'}">
            <slot></slot>
            <div class="actions" >
                <slot name="links"></slot>
            </div>
             <div class="buttons">
                 <slot name="buttn"></slot>
             </div>
        </div>
    </div>
</template>

<script>
   export default {
       props: ['header', 'text', 'theme'],
       methods: {
           closeModal() {
               this.$emit('close')
           }
       },


   }
</script>

<style scoped>

.modal {
    width: 400px;
    padding: 20px;
     margin: 100px auto;
    background: whitesmoke;
    border-radius: 10px;
}

.backdrop {
    top: 0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
}

p{
    color: white;
}

h1{
    color: violet;
    padding: 0;
    border: none;
}

 .sale{
    background: crimson;
    color: white;
}

 .sale h1{
   color: white; 
}
 .modal .actions{
    text-align: center;
    margin: 30px 0 10px 0;
}

  .modal .actions a{
    color: #333;
    padding: 8px;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
    border: 1px solid #eee;
}
 .sale {
    background: crimson;
    color: white;
}

.modal .sale h1 {
    color: white;
}
.modal .sale .actions {
    color: white;
}
.modal .sale .actions a{
    color: white;
}
</style>