<template>

</template>

<script>
    export default {
        mounted() {
            console.log('Group Component mounted.')
        },
        methods : {
            listenForNewGroups() {
                Echo.private('users.' + this.user.id)
                    .listen('GroupCreated', (e) => {
                        this.groups.push(e.group);
                    });
            }
        }
    }
</script>
