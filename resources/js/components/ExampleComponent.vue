<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Example Component</div>

                    <div class="card-body">
                        I'm an example component.
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        mounted() {
            console.log('Component mounted.');
            Echo.join(`chat`)
                .here((users) => {
                    console.log(users);
                })
                .joining((user) => {
                    console.log("joining: " + user.name);
                })
                .leaving((user) => {
                    console.log("leaving: " + user.name);
                })
                .error((error) => {
                    console.error(error);
            });
            console.log('Echo done.');
        }
    }
</script>
