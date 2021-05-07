# desafio02-trilha-nodejs

### checksExistsUserAccount

Esse middleware é responsável por receber o username do usuário pelo header e validar se existe ou não um usuário com o username passado. Caso exista, o usuário é repassado para o request e a função next é chamada.

### checksCreateTodosUserAvailability

Esse middleware recebe o **usuário** já dentro do request e chama a função next apenas se esse usuário ainda estiver no **plano grátis e ainda não possuir 10 *todos* cadastrados** ou se ele **já estiver com o plano Pro ativado**. 

### checksTodoExists

Esse middleware recebe o **username** de dentro do header e o **id** de um *todo* de dentro de `request.params`. Ele valida o usuário, valida se o `id` é um uuid e também valida se esse `id` pertence a um *todo* do usuário informado.
Com todas as validações passando, o *todo* encontrado é passado para o `request` assim como o usuário encontrado também e a função next é chamada.

### findUserById
Esse middleware possui um funcionamento semelhante ao middleware `checksExistsUserAccount` mas a busca pelo usuário é feita através do **id** de um usuário passado por parâmetro na rota. Caso o usuário tenha sido encontrado, o mesmo repassa para dentro do `request.user` e a função é chamada.
