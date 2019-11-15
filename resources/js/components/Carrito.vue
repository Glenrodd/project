<template>
	<div class="card">
		<div class="row">
			<button @click="addItem()" class="btn btn-success">ADICIONAR</button>
			<button @click="removeItems()" class="btn btn-danger">ELIMINAR</button>
		</div>
		<div class="row">
			<table class="table">
				<tr>
					<th>#</th>
					<th>ITEM</th>
					<th>Cantidad</th>
					<th></th>
				</tr>
				<tr v-for="(item,indice) in items" :key="indice">
					<td>{{ item.id }}</td>
					<td>{{ item.name }}</td>
					<td>{{ item.cantidad }}</td>
					<td><button @click="removeItem(indice)" class="btn btn-danger">-</button></td>
				</tr>
			</table>
		</div>
	</div>
</template>
<script type="text/javascript">
	export default {
		data:()=>({
			items: [{id: 1, name: 'prueba', cantidad: 100},{id: 2, name: 'prueba2', cantidad: 200}]
		}),
		mounted(){
			console.log(this.items);
			
		},
		methods:{
			addItem(){
				this.items.push({id: 3, name: 'prueba3', cantidad: 300});
			},
			removeItems(){
				this.items=[];
			},
			removeItem(index){
				this.items.splice(index,1);
			}
		}
	}
</script>