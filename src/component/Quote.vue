<template>
    <div class="col-sm-6 col-md-4 col-lg-3 col-lg-offset-5">
        <!-- <div class="panel panel-default "> -->
            <div class="panel-body quote py-4 px-3 ">
                <slot></slot>
            </div>
        <!-- </div> -->
    </div>
</template>

<script>
export default {
    
}
</script>

<style lang="scss" scoped>
    .panel-body{
        font-family:'Vivaldi'; //'Harlow Solid Italic', cursive;
        font-size:34px;
        color:#6e6e6e;
        box-shadow: 0px 4px 10px rgba(0,0,0, .5);
    }

    .quote{
        cursor:pointer;
        &:hover{
            background:#ffe2e2;
        }
    }


</style>