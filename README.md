# amigo-secreto
//Array para almacenar los nombres de amigos
let amigos = [];

//Funcion para agregar un amigo
function agregarAmigo() {
    const imputamigo = document.getElementById("amigo");
    const nombreAmigo = inputamigo.value.trim(); //Obtiene el valor del campo de entrada y elimina los espacios en blanco al inicio y al final


    //Validar que el nombre no este vacio
    if (nombreAmigo === ""){
        alert("Debes ingresar un nombre"); 
        return; //Detiene la ejecucion de la funcion
    }

//Validar que el nombre no este repetido
if(amigos.includes(nombreAmigo)){
    alert(`El nombre ${nombreAmigo} ya está en la lista de amigos`);
    return;
}

//Agregar el nombre al array de amigos
amigos.push(nombreAmigo);

//Limpiar el campo de entrada
imputamigo.value = "";

//Actualizar la lista en el HTML
actualizarLista();

}

//Funcion para actualizar la lista de amigos en la interfaz
function actualizarLista(){
    const listaAmigos = document.getElementById("lista-amigos");
    
    //Limpiar contenido actual de la lista
    listaAmigos.innerHTML = "";// Borra cualquier contenido previo dentro del contenedor de la lista

    //Recorrer el array con un ciclo for
    for(let i = 0; i < amigos.length; i++){
     const li = document.createElement("li");
     li.textContent = amigos[i];
     listaAmigos.appendChild(li);

    }
}


//Funcion para seleccionar un amigo aleatorio
function sortearAmigo() {
    //Validar que haya al menos un amigo en la lista
    if(amigos.length === 0) { //comprueba si el array esta vacio
        alert("Debes agregar al menos un amigo");
        return;
    }

    //Generar un numero aleatorio
    const indice = Math.floor(Math.random() * amigos.length); //Genera un numero aleatorio entre 0 y el numero de amigos en la lista

    //Obtener el nombre sorteado
    const amigoSorteado = amigos[indicealeatorio]; //usa el indice aleatorio para obtener el nombre del amigo en la lista

    //Mostrar el resultado en html
    const resultado = document.getElementById("resultado");
    resultado.innerHTML = `El amigo seleccionado es: <strong>${amigoSorteado}</strong>`;

}
