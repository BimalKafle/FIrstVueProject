<template>
    <div class="backdrop">
        <div class="modal" :class="{sale: theme==='sale'}">
            <div class="modal-header" >
                <h2>{{header}}</h2>
            </div>
            <hr>
            <p>{{component}}</p>
        </div>
    </div>
</template>

<script>
export default{
    props:['header','component','theme']
}
</script>

<style >
.modal{
    width: 400px;
    padding:20px;
    margin:100px auto;
    background:white;
    border-radius:10px;
}

.modal.sale{
    color: white;
    background: red;
}

.modal-header h2{
    font-size: 10;
    
    margin: 0;
    text-align: start;
}

.backdrop{
    width:100%;
    height:100%;
    top:0;
    position:fixed;
    background:black;
}
</style>