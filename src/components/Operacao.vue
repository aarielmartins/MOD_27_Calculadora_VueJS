<script setup>
    const props = defineProps(['numero1', 'mudaOperador', 'numero2'])
</script>

<template>
    <div class="row d-flex justify-content-center">
        <div class="col-10 d-flex flex-raw justify-content-around">
            <input type="number" required @keyup = "props.numero1" class="w-25 rounded-3 p-2">
            <select @change="props.mudaOperador" class="rounded-3 p-2">
                <option value="+">+</option>
                <option value="-">-</option>
                <option value="/">÷</option>
                <option value="*">×</option>
            </select>
            <input type="number" required @keyup = "props.numero2" class="w-25 rounded-3 p-2" >
        </div>
    </div>
</template>
<style scoped>
select, option{
    color: #8282e6;
    font-weight: 900;
    border: none;

    &:focus{
        outline-color: #8282e6;
    }

}

input{
    color: #8282e6;
    border: none;

    &:focus{
        outline-color: #8282e6;
    }

    &[type=number]::-webkit-inner-spin-button,
    &[type=number]::-webkit-outer-spin-button{
        -webkit-appearance: none;
    }

}
</style>