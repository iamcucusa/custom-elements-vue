<template>
    <div class="angular grid">
        <div class="grid__row">
            <div class="grid__cell--S">
                 <zoom-button :text="'Button 1'" :raet-id="'largeButton'" :type="'button'" v-on:actionClick="handleClick"></zoom-button>
            </div>
            <div class="grid__cell--S">
                 <zoom-button :text="'Button 2'" :raet-id="'secondaryButton'" :mode="'secondary'" v-on:actionClick="handleClick"></zoom-button>
            </div>
            <div class="grid__cell--S">
                <zoom-button :text="'Button 3'" :mode="'link'" :is-disabled="true" :raet-id="'largeButtonDisabled'" v-on:actionClick="handleClick"></zoom-button>
            </div>
        </div>
        <div class="grid__row">
            <div class="grid__cell--S">
                 <zoom-button :text="'toogle action'" :raet-id="'largeButton'" :type="'button'" v-on:actionClick="toogleAction"></zoom-button>
            </div>
            <div class="grid__cell--S">
                <zoom-button :text="'toogle disabled'" :raet-id="'largeButton'" :type="'button'" v-on:actionClick="toogleDisabled"></zoom-button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'HelloWorld',
        props: {
            counter: Number
        },
        data: function () {
            return {
                button: undefined
            }
        },
        methods: {
            handleClick : function(event) {

                this.button = event.detail;
                if(!this.button.isDisabled)
                {
                    this.button.showActive();
                    this.button.showLoading();
                }
                else
                    alert('This button is disabled, enabled it first');

            },
            toogleAction: function () {
                if(this.button)
                {

                    if(this.button.isActive || this.button.isLoading)
                        this.button.done();
                    else {
                        this.button.showActive();
                        this.button.showLoading();
                    }

                }
                else
                    alert('Click one button first');
            },
            toogleDisabled: function () {
                if(this.button)
                {
                    this.button.isDisabled = !this.button.isDisabled;
                }
                else
                    alert('Click one button first');
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h3 {
        margin: 40px 0 0;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }

    .angular {
        border-style: solid;
        border-color: #059991;
        margin: 30px;
        padding-bottom: 20px;
        padding-top: 20px;
    }
</style>
