<template>
    <div :class="{ 'ms-auto': this.message.user == 'userB' }" class=" m-2 borde" style="width: 70%;">
        <p class="fw-bold m-2" :class="{ 'text-end': this.message.user == 'userB' }">@{{ message.name }}</p>
        <div :style="{ backgroundColor: message.color }">
            <p class="m-2 p-1">{{ message.msj }}</p>
            <p class="text-end me-4">{{ message.time }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ChatMessage',
    props: {
        message: Object
    },
};
</script>

<style scoped>
.borde {
    border-radius: 20px;
}

.hr {
    width: 100%;
    height: 3px;
    background-color: white;
    opacity: 0.5
}

</style>
