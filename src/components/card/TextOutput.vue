<template>
    <div @mouseover="showOptions=true" @mouseleave="showOptions=false">
        <transition name="fade">
        <form class="small" v-show="showOptions">
            <label for="selectBox">Font size:</label>
            <select class="custom-select" id="selectBox" v-model="setFontSize">
                <option value="42">42px</option>
                <option value="48">48px</option>
                <option value="56">56px</option>
                <option value="64">64px</option>
            </select>

            <div class="form-check form-check-inline">
                <label class="form-check-label">
                    <input type="radio" class="form-check-input" value="left" v-model="setTextAlign"> Left
                </label>
                <label class="form-check-label">
                    <input type="radio" class="form-check-input" value="Center" v-model="setTextAlign"> Center
                </label>
                <label class="form-check-label">
                    <input type="radio" class="form-check-input" value="right" v-model="setTextAlign"> Right
                </label>               
            </div>

            <div class="form-check form-check-inline">
                <label class="form-check-label">
                    <input type="checkbox" v-model="setBold" class="form-check-input"> Bold
                </label>
            </div>

            <div class="form-check form-check-inline">
                <label class="form-check-label">
                    <input type="checkbox" v-model="setItalic" class="form-check-input"> Italic
                </label>
            </div>
        </form>
        </transition>
        

        <p :style="styleObject" :class="{ bold: setBold, italic: setItalic}">
        {{displayText}}
        </p>
        </div>
</template>

<script>
    export default {
        props: {
            displayText: [String],
            containerHeight: {
                type: Number,
                default: 200
            }
        },
        data: function() {
            return {
                showOptions: false,
                setFontSize: '',
                setTextAlign: '',
                setBold: false,
                setItalic: false
            }
        },
        computed: {
            styleObject: function() {
                return {
                    fontSize: this.setFontSize + 'px',
                    textAlign: this.setTextAlign,
                    height: this.containerHeight + "px",
                    
                }
            }
        }
    }    
</script>

<style scoped>



</style>

