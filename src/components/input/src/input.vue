<template>
    <div :class="$parent.block ? 'layui-input-block' : 'layui-input-inline'">
        <input :type="type"
               :name="name"
               :placeholder="placeholder"
               class="layui-input"
               @input="handleChange"
               :value="value"
               :disabled="disabled"
               :class="{
                'layui-radio-disbaled layui-disabled': disabled
           }">
    </div>
</template>

<script>
	export default {
		name: 'LayInput',
		props: {
			value: [String, Number],
			placeholder: String,
			disabled: Boolean,
			type: {
				type: String,
				default: 'text'
			},
			name: String,
			required: Boolean,
			width: Number
		},
		methods: {
			handleChange: function () {
				if (!this.disabled) {
					this.$emit('input', event.target.value)
				}
			}
		}
	}
</script>

<style>

</style>
