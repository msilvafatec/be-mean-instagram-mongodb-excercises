# MongoDB - Aula 03 - Exercício
autor: Dânio Filho

##  Liste todos Pokemons com a altura menor que 0.5;
```
MacBook-Pro-de-Danio(mongod-3.0.7) be-mean-instagram> var query = { height: { $lt: 0.5}  }
MacBook-Pro-de-Danio(mongod-3.0.7) be-mean-instagram> db.pokemons.find(query)
{
  "_id": ObjectId("56426ef47625928590e6919e"),
  "name": "Pikachu",
  "description": "Rato elétrico bem fofinho",
  "type": "electric",
  "attack": 55,
  "height": 0.4
}
{
  "_id": ObjectId("564270717625928590e6919f"),
  "name": "Bulbassauro",
  "description": "Chicote de trepadeira",
  "type": "grama",
  "attack": 49,
  "height": 0.4
}
{
  "_id": ObjectId("564272a87625928590e691a3"),
  "name": "Caterpie",
  "description": "Larva lutadora",
  "type": "inseto",
  "attack": 30,
  "height": 0.3
}
Fetched 3 record(s) in 4ms
```

## Liste todos Pokemons com a altura maior ou igual que 0.5;

```
MacBook-Pro-de-Danio(mongod-3.0.7) be-mean-instagram> var query = { height: { $gte: 0.5}  }
MacBook-Pro-de-Danio(mongod-3.0.7) be-mean-instagram> db.pokemons.find(query)
{
  "_id": ObjectId("564270717625928590e691a0"),
  "name": "Charmander",
  "description": "Esse é o cão chupando manga de fofinho",
  "type": "fogo",
  "attack": 52,
  "height": 0.6
}
{
  "_id": ObjectId("564270737625928590e691a1"),
  "name": "Charmander",
  "description": "Esse é o cão chupando manga de fofinho",
  "type": "fogo",
  "attack": 52,
  "height": 0.6
}
{
  "_id": ObjectId("564271587625928590e691a2"),
  "name": "Squirtle alterado",
  "description": "Ejeta água que passarinho não bebe",
  "type": "água",
  "attack": 48,
  "height": 0.5
}
Fetched 3 record(s) in 6ms
```

## Liste todos Pokemons com a altura menor ou igual que 0.5 E do tipo grama;

```
MacBook-Pro-de-Danio(mongod-3.0.7) be-mean-instagram> var query = { height: { $lte: 0.5}, $and: [{type: 'grama'}]  }
MacBook-Pro-de-Danio(mongod-3.0.7) be-mean-instagram> db.pokemons.find(query)
{
  "_id": ObjectId("564270717625928590e6919f"),
  "name": "Bulbassauro",
  "description": "Chicote de trepadeira",
  "type": "grama",
  "attack": 49,
  "height": 0.4
}
Fetched 1 record(s) in 3ms
```

## Liste todos Pokemons com o name `Pikachu` OU com attack menor ou igual que 0.5;

```
MacBook-Pro-de-Danio(mongod-3.0.7) be-mean-instagram>  var query = {  $or: [ { name: 'Pikachu' }, { attack: { $lte: '0.5' } } ] }
MacBook-Pro-de-Danio(mongod-3.0.7) be-mean-instagram> db.pokemons.find(query)
{
  "_id": ObjectId("56426ef47625928590e6919e"),
  "name": "Pikachu",
  "description": "Rato elétrico bem fofinho",
  "type": "electric",
  "attack": 55,
  "height": 0.4
}
Fetched 1 record(s) in 4ms
```

## Liste todos Pokemons com o attack MAIOR OU IGUAL QUE 48 E com  height menor ou igual que 0.5;
 
```
MacBook-Pro-de-Danio(mongod-3.0.7) be-mean-instagram> var query = { $and: [ { attack: { $gte: 48 }, height: { $lte: 0.5 } } ] }
MacBook-Pro-de-Danio(mongod-3.0.7) be-mean-instagram> db.pokemons.find(query)
{
  "_id": ObjectId("56426ef47625928590e6919e"),
  "name": "Pikachu",
  "description": "Rato elétrico bem fofinho",
  "type": "electric",
  "attack": 55,
  "height": 0.4
}
{
  "_id": ObjectId("564270717625928590e6919f"),
  "name": "Bulbassauro",
  "description": "Chicote de trepadeira",
  "type": "grama",
  "attack": 49,
  "height": 0.4
}
{
  "_id": ObjectId("564271587625928590e691a2"),
  "name": "Squirtle alterado",
  "description": "Ejeta água que passarinho não bebe",
  "type": "água",
  "attack": 48,
  "height": 0.5
}
Fetched 3 record(s) in 4ms

```
