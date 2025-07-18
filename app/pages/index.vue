<template>
    <div class="w-full h-screen flex items-center justify-center">
        <Button class="w-32" @click="handleClick">Test Button</Button>
    </div>
</template>
<script setup>
import { toast } from 'vue-sonner'
const handleClick = () => {
    toast.warning('Event has been created', {
        description: 'December 03, 2023 at 9:00 AM',
        action: {
            label: 'Got it!',
            onClick: () => console.log('User clicked the action button'),
        },
    })
}
</script>