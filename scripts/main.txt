const chk = document.getElementById('chk');

chk.addEventListener('change', () => {
	document.body.classList.toggle('dark');
});





let miBoton = document.querySelector('button');
let miTitulo = document.querySelector('h1');

function estableNombreUsuario(){
	let miNombre = prompt('Por favor, ingrese su nombre');
	if(!miNombre){
		estableNombreUsuario();
	} else{
		localStorage.setItem('nombre', miNombre);
		miTitulo.innerHTML = 'Bienvenido ' + miNombre;
	}
}

if(!localStorage.getItem('nombre')){
	estableNombreUsuario();
} else{
	let nombreAlmacenado = localStorage.getItem('nombre');
	miTitulo.textContent = 'Bienvenido ' + nombreAlmacenado;
}

miBoton.onclick = function(){
	estableNombreUsuario();
}