<template>
	<div class="tree-view-item">
		<div v-if="isObject(data)" class="tree-view-item-leaf">
			<div class="tree-view-item-node" @click.stop="toggleOpen()">
				<span :class="{opened: isOpen()}" class="tree-view-item-key tree-view-item-key-with-chevron">{{getKey(data)}}</span>
				<span class="tree-view-item-hint" v-show="!isOpen() && data.children.length === 1">{{data.children.length}} property</span>
				<span class="tree-view-item-hint" v-show="!isOpen() && data.children.length !== 1">{{data.children.length}} properties</span>
			</div>
			<tree-view-item :key="getKey(child)" :max-depth="maxDepth" :current-depth="currentDepth+1" v-show="isOpen()" v-for="child in data.children" :data="child" :modifiable="modifiable" :link="link" :errorword="errorword" @change-data="onChangeData"></tree-view-item>
		</div>
		<div v-if="isArray(data)" class="tree-view-item-leaf">
			<div class="tree-view-item-node" @click.stop="toggleOpen()">
				<span :class="{opened: isOpen()}" class="tree-view-item-key tree-view-item-key-with-chevron">{{getKey(data)}}</span>
				<span class="tree-view-item-hint" v-show="!isOpen() && data.children.length === 1">{{data.children.length}} item</span>
				<span class="tree-view-item-hint" v-show="!isOpen() && data.children.length !== 1">{{data.children.length}} items</span>
			</div>
			<tree-view-item :key="getKey(child)" :max-depth="maxDepth" :current-depth="currentDepth+1" v-show="isOpen()" v-for="child in data.children" :data="child" :modifiable="modifiable" :link="link" :errorword="errorword" @change-data="onChangeData"></tree-view-item>
		</div>
		<tree-view-item-value v-if="isValue(data)" class="tree-view-item-leaf" :key-string="getKey(data)" :data="data.value" :modifiable="modifiable" :link="link" :errorword="errorword" @change-data="onChangeData"></tree-view-item-value>
	</div>
</template>

<script>
	import _ from 'lodash'
	import TreeViewItemValue from './TreeViewItemValue.vue'

	export default {
		components: {
			TreeViewItemValue
		},
		name: "tree-view-item",
		props: ["data", "max-depth", "current-depth", "modifiable", "link", "errorword"],
		data: function() {
			return {
				open: this.currentDepth < this.maxDepth
			}
		},
		methods: {
			isOpen: function() {
				return this.open;
			},
			toggleOpen: function() {
				this.open = !this.open;
			},
			isObject: function(value) {
				return value.type === 'object';
			},
			isArray: function(value) {
				return value.type === 'array';
			},
			isValue: function(value) {

				return value.type === 'value';
			},
			getKey: function(value) {
				if(_.isInteger(value.key)) {
					return value.key + ":";
				} else {
					return "\"" + value.key + "\":";
				}
			},
			isRootObject: function(value = this.data) {
				return value.isRoot;
			},
			onChangeData: function(path, value) {
				path = _.concat(this.data.key, path)
				this.$emit('change-data', path, value)
			}
		}
	};
</script>

<style scoped>
	.tree-view-item {
		font-family: helvitica monaco, monospace;
		margin-left: 18px;
		padding: 3px 5px 3px 20px;
		font-size: 12px;
		line-height: 18px;
		letter-spacing: 0.5px;
	}
	
	.tree-view-item-node {
		cursor: pointer;
		position: relative;
		white-space: nowrap;
		text-align: left;
	}
	
	.tree-view-item-leaf {
		white-space: normal;
		word-break: break-all;
		text-align: left;
		display: block;
	}
	
	.tree-view-item-key {
		vertical-align: top;
		font-weight: initial;
	}
	
	.tree-view-item-key-with-chevron {
		padding-left: 14px;
	}
	
	.tree-view-item-key-with-chevron.opened::before {
		top: 4px;
		transform: rotate(90deg);
		-webkit-transform: rotate(90deg);
	}
	
	.tree-view-item-key-with-chevron::before {
		color: #444;
		content: '\25b6';
		font-size: 10px;
		left: 1px;
		position: absolute;
		top: 3px;
		transition: -webkit-transform .1s ease;
		transition: transform .1s ease;
		transition: transform .1s ease, -webkit-transform .1s ease;
		-webkit-transition: -webkit-transform .1s ease;
	}
	
	.tree-view-item-hint {
		color: #ccc
	}
</style>