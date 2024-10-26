<template>
    <div  :class="{ 'ms-auto': this.message.user == 'userB' }" class="w-75 m-2 borde">
            <p class="fw-bold m-2" :class="{ 'text-end': this.message.user == 'userB' }" >@{{ message.name }}</p>
            <div :style="{ backgroundColor: message.color }">
                <span class="m-2 cw" :class="{ 'text-end': this.message.user == 'userB' }" >{{ message.msj }}</span>
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
.borde{
    border-radius: 20px;
}
.hr{
    width: 100%;
    height: 3px;
    background-color: white;
    opacity: 0.5
}

.cw{
    width: max-content
}
</style>
