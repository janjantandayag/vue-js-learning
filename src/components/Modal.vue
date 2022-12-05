<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal">
            <slot>Tet</slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
            <div class="disclaimerAction">
                <slot name="disclaimer">

                </slot>
            </div>
        </div>
    </div>    
</template>

<script>
    export default {
        props: [],

        methods: {
            closeModal(){
                this.$emit('close');
            }
        }
    }
</script>

<style>
    .modal{
        width: 400px;
        padding:20px;
        margin:100px auto;
        background: #fff;
        border-radius: 10px;
    }

    .backdrop{
        top:0;
        position:fixed;
        background: rgba(0, 0, 0, 0.5);
        width: 100%;
        height: 100%;
    }

    .modal h1{
        color:rgb(30, 142, 105);
        border-bottom: none;
    }

    .modal .actions a{
        color: rgb(7, 150, 107);
        padding: 5px 10px;
        border: 1px solid #bbb;
        border-radius: 3px;
        text-decoration: none;
        margin-left: 10px;
    }

    .sale{
        background: crimson;
        color:#fff
    }

    .sale h1{
        color: #fff;
    }

    .disclaimerAction {
        font-size:9px;
        font-style: italic;
        margin-top: 20px;
    }

</style>