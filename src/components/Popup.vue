<template>
    <div class="backdrop" @click.self="closePopup">
        <div class="popup" :class="{evil: boop === 'evil'}">
            <h1>this is a popup</h1>
            <p>{{ message }}</p><p>{{ couler }}</p>
            <input type="text" v-model="boop">

        </div>
    </div>
</template>
<script>
export default {
    props: ['message', 'couler','inputColour'],
    data () {
        return {
            boop: ''
        }
    },
    methods: {
        closePopup() {
            this.$emit('closer')
        }
    },
    }

</script>
<style scoped>
.backdrop {
  display: block; /* Hidden by default */
  position: fixed; /* Stay in place */
  z-index: 1; /* Sit on top */
  left: 0;
  top: 0;
  width: 100%; /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgb(0,0,0); /* Fallback color */
  background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
}

/* Modal Content/Box */
.popup {
  background-color: #fefefe;
  margin: 15% auto; /* 15% from the top and centered */
  padding: 20px;
  border: 1px solid #888;
  width: 80%; /* Could be more or less, depending on screen size */
}

.evil {
    color: red;
    background-color: orange;
}
</style>