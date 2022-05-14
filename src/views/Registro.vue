<template>
	<h1 class="my-5">Registro de Usuarios</h1>
	<form>
		<input
			class="form-control my-2"
			type="email"
			placeholder="email"
			v-model.trim="email"
		/>
		<input
			class="form-control my-2"
			type="password"
			placeholder="password"
			v-model.trim="pass1"
		/>
		<input
			class="form-control my-2"
			type="password"
			placeholder="password"
			v-model.trim="pass2"
		/>
		<button class="btn btn-primary" type="submit" :disabled="bloquear">
			Registrar
		</button>
	</form>
</template>

<script>
export default {
	data() {
		return {
			email: '',
			pass1: '',
			pass2: '',
		}
	},
    computed: {
        bloquear(){
            if(!this.email.includes('@')){
                return true
            }
            if(this.pass1.length > 5 && this.pass1 === this.pass2){
                return false
            }
            return true
        }
    }
}
</script>
