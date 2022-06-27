# actividadjs



/**
 * !=======================================
 * !Estamos llegando a la finalización del curso de Javascript Vanilla
 * !y vamos a realizar un repaso de los temas vistos mediante un ejercicio
 * !integrador conectadonos con Api...
 *
 * !Para eso deberas realizar las siguientes consignas siguiendo las buenas practicas vistas en clase
 * !y utilizando todo el conocimiento aprendido en clases anteriores...
 *
 * * ...
 *
 * !Comencemos.
 * !===========================================
 */

/**
 * *=====================================
 * *            PRIMERA  PARTE
 * *-------------------------------------
 */

/**
 * Vamos a trabajar con PokeApi. La Api de Pokemon.
 * ? 1) Almacenar la base url en una constante.
 */


 <!-- const BASE_URL = 'https://pokeapi.co/api/v2/' -->

 
 


// todo: todo: Code here

/**
 * ? 2) Crear la configuración de un fetch para ejecutar en una consola del navegador.
 */

 <!-- const BASE_URL = 'https://pokeapi.co/api/v2/'

 const opts = {
     method: 'GET',
     headers: {
         'Content-Type': 'application/json'
     }
 }
 
 const getpokemon = async () => {
     const pokemon = await fetch(`${BASE_URL}/pokemon/`, opts)
 
     return pokemon.json()
 }
 
 const pokemon = await getpokemon()
 
 console.log('pokemon', pokemon) -->
 


// todo: Code here

/**
 * ? 3) Realizar una busqueda de los primeros 20 pokemones
 */


<!-- const getPokemons = async () => {
    const pokemons = await fetch(`${BASE_URL}/pokemon?limit=30`, opts)

    return pokemons.json()
}

const pokemons = await getPokemons()

console.log('pokemon')
console.log('Respuesta', pokemons.results)
console.log('pokemon') -->




// todo: Code here


/**
 * ? 4) Buscar al pokemon 'Charmander', armar un objeto literal con las siguientes propiedades de este pokemon:
 *      id, name, tipo y almenos 2 movimientos
*       Luego mostrar por consola
 */
 
 <!-- const result = pokemons.results.find(p => p.name == 'charmander')
console.log()
console.log('Encontrando a charmander', result)

const getCharmanderDetails = async()=> {
    const details = await fetch(result.url, opts)
    return details.json()
}

const charmanderDetails = await getCharmanderDetails()

const charmander = {
    id : charmanderDetails.id,
    name: charmanderDetails.name,
    type: charmanderDetails.types.map(d => d.type.name).join(' , '),
    moves: charmanderDetails.moves.map(d => d.move.name).join(' , ')

}
console.log('pokemon: ', charmander)
console.log() -->



// todo: Code here

/**
 * ? 5) Obtener la cadena de evoluciones de Charmander
 */


 <!-- const getCharmanderSpecies = async()=> {
    const species = await fetch(`${BASE_URL}/pokemon-species/${charmander.name}`, opts)
    return species.json()
}

const speciesCharmander = await getCharmanderSpecies()

const getCharmanderEvolutions = async()=> {
    const evolutions = await fetch(speciesCharmander.evolution_chain.url, opts)
    return evolutions.json()
}

const evolutionsCharmander = await getCharmanderEvolutions()

const capitalize = (evolution) =>  evolution[0].toUpperCase() + evolution.substring(1)

console.log()
console.log(`Evoluciones de Charmander:
Primera: ${capitalize(evolutionsCharmander.chain.species.name)},
Segunda: ${capitalize(evolutionsCharmander.chain.evolves_to[0].species.name)},
Tercera: ${capitalize(evolutionsCharmander.chain.evolves_to[0].evolves_to[0].species.name)}`)
console.log() -->

// todo: Code here

/**
 * *=====================================
 * *            SEGUNDA  PARTE
 * *-------------------------------------
 */


/**
 * ? 6) Indicar cual es el id del tipo psiquico. Armar un objeto con las características que consideres importantes del tipo electrico
 */


 <!-- const getTypes = async()=> {
    const types = await fetch(`${BASE_URL}/type`, opts)
    return types.json()
}

const types = await getTypes()

const psychicObject = types.results.find( t => t.name == 'psychic')

const getPsychicId = async()=> {
    const psychicResults = await fetch(psychicObject.url, opts)
    return psychicResults.json()
}
const psychicResults = await getPsychicId();

const electricObject = types.results.find( t => t.name == 'electric')

const getElectricDetails = async()=> {
    const electricDetails = await fetch(electricObject.url, opts)
    return electricDetails.json()
}
const electricDetails = await getElectricDetails();

const pokemonsElectrics = {

    names : electricDetails.pokemon.map(p => p.pokemon.name).join(' , '),
    game_indices: electricDetails.game_indices.map(g => g.generation.name).join(' , '),
    moves: electricDetails.moves.map(m => m.name).join(' , ')
}

console.log()
console.log('Respuesta: ')
console.log('El id del tipo psiquico es:', psychicResults.id)
console.log('Caracteristicas de pokemons Electricos:', pokemonsElectrics)
console.log() -->

// todo: Code here

/**
 * ? 7) Indicar cuantos pokemons electricos hay, y crear objetos literales con alguna descripción de 5 de estos pokemons electricos
 */

 <!-- const pokemonElectrics2 = []
for(let i=0; i < 5; i++ )
{
    pokemonElectrics2.push(electricDetails.pokemon[i])
}

const urls = pokemonElectrics2.map(p => p.pokemon.url);


const getPokemonElectricDetails = async(url)=> {

    const electricDetails = await fetch(url, opts)
    return electricDetails.json();
}

const detailsPokemonsElectric  = [];
for(url of urls)
{
    let results = await getPokemonElectricDetails(url)
    detailsPokemonsElectric.push({
        id : results.id,
        name: results.name,
        type: results.types.map(d => d.type.name).join(' , '),
        moves: results.moves.map(d => d.move.name).join(' , ')
    })
}
console.log()
console.log('Respuesta:')
console.log('La cantidad de pokemons electricos es:', electricDetails.pokemon.length)
console.log('Caracteristicas de 5 Pokemons electricos: ', detailsPokemonsElectric)
console.log() -->

// todo: Code here

/**
 * ? 8) Que hay de particular en la especie del pokemon Lugia
 */



 <!-- const getLugiaType = async()=> {
    const types = await fetch(`${BASE_URL}/pokemon-species/lugia`, opts)
    return types.json()
}

const lugiaType = await getLugiaType()

console.log()
console.log('Respuesta:')
console.log(lugiaType.is_legendary ? 
    'Lugia es una especie legendaria' : 
    'Lugia no es una especie legendaria')
    console.log() -->





// todo: Code here
