# Comandos para CRUD

## Create
~~~shell

db.[collection].insertOne( valores )

# exemplos

$ db.pessoas.insertOne({name: "Marllon"})

# Inserção em massa ordenada
$ db.pessoas.insert([{name: "João"}, {name:"Maria"}])

# Inserção em massa não ordenada
$ db.pessoas.insert([{name: "Pedro"}, {name:"Gabriela"}, {name: "Ana"}], {ordered: false})

$ db.pessoas.insert({name: "Luiz", endereco: {"cidade": "São Paulo"}})
~~~

## READ

~~~shell
# Retorna um único documento
$ db.pessoas.findOne()

# Retorna um cursor
$ db.pessoas.find()

# Formata saída
$db.pessoas.find().pretty()

# AND lógico implícito
$ db.pessoas.find({name: "Marllon", age: 26})
~~~

## UPDATE
~~~shell

# Aviso: substitui todo documento
$ db.pessoas.update({"_id": 1}, {"year": 1994})

$ db.pessoas.update({"_id": 1}, {$set: {"year": 1994, "age": 26}})
~~~