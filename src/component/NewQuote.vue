<template>
    <div class="row mb-5">
        <form class="col-sm-12">
            <div class="col-sm-8 form-group mx-auto">
                <label  class="form-text">Quote</label>
                <input type="text" class="form-control" v-model="quote"/>
            </div>
            <div class="form-group col-sm-4 mx-auto text-center">
                <button class="btn btn-primary px-4" @click.prevent='createQuote'>Add Quote</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    props: ['quotes'],
    data: function(){
        return{
            quote: ''
        }

    },
    methods: {
        createQuote: function(){
            this.$emit('addQuote', this.quote);
            this.quote = ''
            
        }
    }
}
</script>

<style lang="scss" scoped>

</style>