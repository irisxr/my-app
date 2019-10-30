<template>
    <div>
        <select
                :value="personInfo.areaCode"
                placeholder="区号"
                @change="handleSelectFlume"
        >
            <option value="+86">+86</option>
            <option value="+60">+60</option>
        </select>

        <input
                placeholder="手机号"
                :value="personInfo.phoneNum"
                type="number"
                @input="handlePhoneNum"
        >

        <input
                :value="zipCode"
                type="number"
                placeholder="邮编"
                @input="handleZipCode"
        >
    </div>
</template>

<script>
    export default {
        props: {
            personInfo: Object,
            zipCode: String
        },
        methods: {
            handleSelectFlume(e) {
                this.$emit('change', {
                    ...this.personInfo,
                    areaCode: e.target.value
                })
            },
            handlePhoneNum(e) {
                this.$emit('change', {
                    ...this.personInfo,
                    phoneNum: e.target.value
                })
            },
            handleZipCode(e) {
                this.$emit('update:zipCode', e.target.value)
            }
        }
    }
</script>