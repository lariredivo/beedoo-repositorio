A documentação a seguir apresenta os user stories, os critérios de aceite, os cenários e casos de teste. Também inclui os links solicitados: a planilha Excel com os testes, a pasta com os vídeos de evidências e o link da documentação da segunda etapa deste processo. Para facilitar a relação entre os documentos, os testes são identificados por IDs (por exemplo, CAD-0001 indica o primeiro teste da parte de cadastro de novos cursos e LIS-0001 indica o primeiro teste da parte de listagem de cursos).


## Users story do formulário de inscrição do Beedoo

### Decisões tomadas para a criação do user story
As decisões foram baseadas em diversos pontos cruciais. Primeiramente, considerou-se que, ao estabelecer condições de teste, é possível investigar generalizações, contradições e ambiguidades, ajudando a esclarecer as necessidades do sistema. Além disso, o fluxo de cadastro e listagem de cursos deve ser intuitivo e eficiente para os usuários, o que levou à divisão do user story em duas partes, correspondendo às duas páginas da plataforma. Outro ponto importante é que o sistema deve validar os dados inseridos nos inputs para evitar erros e inconsistências. Por fim, para melhor orientar os usuários, as mensagens de erro e sucesso devem ser claras e informativas.

---
## Users story
### Users story 1 - Cadastro de curso

* Como um administrador da plataforma do Beedoo QA Chalenge
* Eu quero cadastrar novos cursos
* Para que sejam oferecidos aos alunos

**Critérios de aceite:** 
1. Deve haver um formulário para o cadastro de cursos com os seguintes campos obrigatórios: 
- Nome do curso 
- Descrição do curso
 - Instrutor 
- URL da imagem da capa
- Data de início 
- Data de fim 
- Número de vagas
- Tipo de curso: online ou presencial. Caso seja escolhido o curso presencial, deve ser necessário colocar o endereço. Já no online deverá ser solicitado o link da inscrição.

2. O sistema só deve permitir o cadastro após validar que todos os campos obrigatórios foram preenchidos, pois não deve ser possível criar um curso sem nenhuma informação.

3. Caso o curso seja cadastrado com sucesso, deve aparecer a mensagem "Curso cadastrado com sucesso!"

4. Em caso de erro no cadastro, o sistema deve exibir mensagens de erro considerando:
	- Falta de preenchimento de algum campo com mensagem específica
-Erro na finalização do cadastro por algum outro motivo (diferenciar essa mensagem)
  
### Casos e cenários de testes
**Caso 1: Cadastro bem-sucedido de um novo curso**
* Dado que o administrador está na página de cadastro de curso
* Quando o administrador preenche todos os campos obrigatórios
* E clica no botão "Cadastrar curso"
* Então o curso deve ser salvo no banco de dados
* E a mensagem "Curso cadastrado com sucesso!" deve ser exibida
* E o administrador deve ser redirecionado para a página de listagem de cursos

**CAD-0001 - Cenário de teste 1: Criação bem-sucedida de um curso presencial**
* Passo 1: Acessar o link https://creative-sherbet-a51eac.netlify.app/ 
* Passo 2: Clicar a aba "Cadastrar curso" 
* Passo 3: Preencher o nome do curso
* Passo 4: Preencher a descrição do curso
* Passo 5: Preencher o nome do instrutor
* Passo 6: Preencher a url da capa do curso
* Passo 7: Inserir a data de início do curso 
* Passo 8: Inserir a data de fim do curso 
* Passo 9: Preencher o número de vagas
* Passo 10: Selecionar o tipo de curso presencial
* Passo 11: Inserir o endereço
* Passo 12: Clicar no botão "Cadastrar curso"
* Passo 13: Confirmar a exibição da mensagem de confirmação de cadastro
* Passo 14: Redirecionamento para a página de listagem de cursos 
					
**CAD-0002 - Cenário de teste 2: Criação bem-sucedida de um curso online**
* Passo 1: Acessar o link https://creative-sherbet-a51eac.netlify.app/ 
* Passo 2: Clicar a aba "Cadastrar curso" 
* Passo 3: Preencher o nome do curso
* Passo 4: Preencher a descrição do curso
* Passo 5: Preencher o nome do instrutor
* Passo 6: Preencher a url da capa do curso
* Passo 7: Inserir a data de início do curso 
* Passo 8: Inserir a data de fim do curso 
* Passo 9: Preencher o número de vagas
* Passo 10: Selecionar o tipo de curso online
* Passo 11: Inserir o link de inscrição
* Passo 12: Clicar no botão "Cadastrar curso"
* Passo 13: Confirmar a exibição da mensagem de confirmação de cadastro
* Passo 14: Redirecionamento para a página de listagem de cursos 

**Caso 2: Falha no cadastro de curso devido ao curso já existir**
* Dado que o administrador está na página de cadastro de curso
* Quando o administrador preenche os campos do formulário com os mesmos dados de um curso já existente.
* E clica no botão "Cadastrar curso"
* Então o sistema deve exibir uma mensagem de erro: "Este curso já está cadastrado. Por favor, verifique os dados e tente novamente."

**CAD-0003 - Cenário de teste 3: Impossibilidade de criar um curso presencial já existente**
* Passo 1: Acessar o link https://creative-sherbet-a51eac.netlify.app/ 
* Passo 2: Clicar a aba "Cadastrar curso" 
* Passo 3: Preencher o nome de um curso já cadastrado
* Passo 4: Preencher a descrição do curso já cadastrado
* Passo 5: Preencher o nome do instrutor
* Passo 6: Preencher a url da capa do curso
* Passo 7: Inserir a data de início do curso já cadastrada
* Passo 8: Inserir a data de fim do curso já cadastrada
* Passo 9: Preencher o número de vagas
* Passo 10: Selecionar o tipo de curso presencial
* Passo 11: Inserir o endereço
* Passo 12: Clicar no botão "Cadastrar curso"
*Passo 13: Confirmar a exibição da mensagem de erro indicando que o curso já foi cadastrado anteriormente. A mensagem deve ser: "Erro: Este curso já está cadastrado. Por favor, verifique os dados e tente novamente."
* Passo 14: Redirecionamento para a página de listagem de cursos 

**CAD-0004 - Cenário de teste 4: Impossibilidade de criar um curso online já existente**
* Passo 1: Acessar o link https://creative-sherbet-a51eac.netlify.app/ 
* Passo 2: Clicar a aba "Cadastrar curso" 
* Passo 3: Preencher o nome de um curso já cadastrado
* Passo 4: Preencher a descrição do curso já cadastrado
* Passo 5: Preencher o nome do instrutor
* Passo 6: Preencher a url da capa do curso
* Passo 7: Inserir a data de início do curso já cadastrada
* Passo 8: Inserir a data de fim do curso já cadastrada
* Passo 9: Preencher o número de vagas
* Passo 10: Selecionar o tipo de curso online
* Passo 11: Inserir o link de inscrição
* Passo 12: Clicar no botão "Cadastrar curso"
* Passo 13: Confirmar a exibição da mensagem de erro indicando que o curso já foi cadastrado anteriormente. A mensagem deve ser: "Erro: Este curso já está cadastrado. Por favor, verifique os dados e tente novamente."

**Caso 3: Falha no cadastro de curso devido a campo obrigatório não preenchido** 
* Dado que o administrador está na página de cadastro de curso
* Quando o administrador não preenche todos os campos obrigatórios
* E clica no botão "Cadastrar curso"
* Então o sistema deve exibir uma mensagem de erro "Erro ao cadastrar o curso. Preencha os campos obrigatórios"

**CAD-0005 - Cenário de teste 5: Impossibilidade de criar um curso sem nenhuma informação**
* Passo 1: Acessar o link https://creative-sherbet-a51eac.netlify.app/ 
* Passo 2: Clicar a aba "Cadastrar curso" 
* Passo 3: Não preencher o nome de um curso
* Passo 4: Não preencher a descrição do curso 
* Passo 5: Não preencher o nome do instrutor
* Passo 6: Não preencher a url da capa do curso
* Passo 7: Não inserir a data de início do curso
* Passo 8: Não inserir a data de fim do curso 
* Passo 9: Não preencher o número de vagas
* Passo 10: Não selecionar o tipo de curso 
* Passo 11: Clicar no botão "Cadastrar curso"
* Passo 12: Confirmar a exibição da mensagem de erro indicando que o curso não pode ser criado sem nenhuma informação. A mensagem deve ser: "Erro: Preencha as informações obrigatórias e tente novamente."

**Caso 4: Validação dos campos do formulário de cadastro de curso**
* Dado que o administrador está na página de cadastro de curso
* Quando o administrador preenche os campos do formulário com valores inválidos
* Então o sistema deve impedir a criação do curso
* E exibir as mensagens de erro conforme o campo

**CAD-0006 - Cenário de teste 6: Validação do campo do nome do curso**
* Passo 1: Acessar o link https://creative-sherbet-a51eac.netlify.app/ 
* Passo 2: Clicar a aba "Cadastrar curso" 
* Passo 3: Preencher o campo "Nome do Curso" com um valor com menos de 3 caracteres ou mais de 100
* Passo 4: Clicar no botão "Cadastrar curso"
* Passo 5: Confirmar a exibição da mensagem de erro indicando que o curso não pode ser criado sem seguir a validação. A mensagem deve ser: "O nome do curso deve ter entre 3 e 100 caracteres."

**CAD-0007 - Cenário de teste 7: Validação do campo da descrição do curso**
* Passo 1: Acessar o link https://creative-sherbet-a51eac.netlify.app/ 
* Passo 2: Clicar a aba "Cadastrar curso" 
* Passo 3: Preencher o campo "Descrição do Curso" com um valor com menos de 10 caracteres
* Passo 4: Clicar no botão "Cadastrar curso"
* Passo 5: Confirmar a exibição da mensagem de erro indicando que o curso não pode ser criado sem seguir a validação. A mensagem deve ser: "A descrição do curso deve ter no mínimo 10 caracteres."

**CAD-0008 - Cenário de teste 8: Validação do campo do instrutor**
* Passo 1: Acessar o link https://creative-sherbet-a51eac.netlify.app/
* Passo 2: Clicar na aba "Cadastrar curso"
* Passo 3: Preencher o campo "Instrutor" com um valor que contenha caracteres especiais ou números
* Passo 4: Clicar no botão "Cadastrar curso"
* Passo 5: Confirmar a exibição da mensagem de erro indicando que o curso não pode ser criado sem seguir a validação. A mensagem deve ser: "O campo 'Instrutor' deve conter apenas letras."

**CAD-0009 - Cenário de teste 9: Validação do campo da URL da imagem da capa**
* Passo 1: Acessar o link https://creative-sherbet-a51eac.netlify.app/
* Passo 2: Clicar na aba "Cadastrar curso"
* Passo 3: Preencher o campo "URL da imagem da capa" com uma URL inválida (por exemplo, um link que não aponta para uma imagem ou um link com formato incorreto)
* Passo 4: Clicar no botão "Cadastrar curso"
* Passo 5: Confirmar a exibição da mensagem de erro indicando que o curso não pode ser criado sem seguir a validação. A mensagem deve ser: "A URL da imagem deve ser válida e apontar para uma imagem."

**CAD-0010 - Cenário de teste 10: Validação do campo da data de fim**
* Passo 1: Acessar o link https://creative-sherbet-a51eac.netlify.app/
* Passo 2: Clicar na aba "Cadastrar curso"
* Passo 3: Preencher o campo "Data de início" com uma data válida (por exemplo, 2024-08-01)
* Passo 4: Preencher o campo "Data de fim" com uma data anterior à data de início (por exemplo, 2024-07-31)
* Passo 5: Clicar no botão "Cadastrar curso"
* Passo 6: Confirmar a exibição da mensagem de erro indicando que o curso não pode ser criado sem seguir a validação. A mensagem deve ser: "A data de fim não pode ser anterior à data de início."

**CAD-0011 - Cenário de teste 11: Validação do campo do número de vagas**
- Passo 1: Acessar o link https://creative-sherbet-a51eac.netlify.app/
- Passo 2: Clicar na aba "Cadastrar curso"
- Passo 3: Preencher o campo "Número de vagas" com um valor que não seja um número inteiro positivo (por exemplo, -10.37)
- Passo 4: Clicar no botão "Cadastrar curso"
- Passo 5: Confirmar a exibição da mensagem de erro indicando que o curso não pode ser criado sem seguir a validação. A mensagem deve ser: "O número de vagas deve ser um número inteiro positivo."
  
**CAD-0012 - Cenário de teste 12: Validação do campo do link de inscrição do curso online**
* Passo 1: Acessar o link https://creative-sherbet-a51eac.netlify.app/
* Passo 2: Clicar na aba "Cadastrar curso"
* Passo 3: Selecionar a opção "Online" para o tipo de curso
* Passo 4: Preencher o campo "Link de inscrição" com um valor que não é uma URL
* Passo 5: Clicar no botão "Cadastrar curso"
* Passo 6: Confirmar a exibição da mensagem de erro indicando que o curso não pode ser criado sem seguir a validação. A mensagem deve ser: "O link de inscrição deve estar no formato correto (http:// ou https://)."


### Users story 2 - Listagem de cursos

* Como um administrador da plataforma do Beedoo QA Chalenge
* Eu quero visualizar a listagem dos cursos
* Para que eu possa verificar os cursos disponíveis

**Critérios de aceite:** 
1. Para que um curso possa ser visualizado na listagem, ele deve ter sido criado previamente.

2. A listagem deve exibir as seguintes informações de cada curso:
- Nome do curso 
- Imagem da capa
- Data de início 
- Data de fim 
- Número de vagas
- Tipo de curso: online ou presencial

3. Os cursos devem ser listados em ordem cronológica de criação, do mais recente ao mais antigo. 

4. Deve ser possível excluir um curso.

### Casos e cenários de testes
**Caso 1: Exibição das informações do curso na listagem**
- Dado que o administrador está na página de listagem de cursos
- E a listagem de cursos já estar pré-populada
- Quando o administrador visualiza a lista de cursos
- Então o sistema deve exibir todas as informações listadas nos critérios de aceite
- E todas as informações devem ser visíveis

**LIS-0001 - Cenário de teste 1: Exibição das informações do curso na listagem**
- Passo 1: Acessar o link https://creative-sherbet-a51eac.netlify.app/
- Passo 2: Verificar se as seguintes informações estão visíveis para cada curso:
   - Nome do curso
   - Descrição do curso
   - Instrutor
   - Imagem da capa
   - Data de início
   - Data de fim
   - Número de vagas
   - Tipo de curso: online ou presencial

**Caso 2: Ordem cronológica de criação dos cursos na listagem**
- Dado que o administrador está na página de listagem de cursos
- E a listagem de cursos já estar pré-populada
- Quando o administrador visualiza a lista de cursos
- Então o sistema deve exibir os cursos em ordem cronológica de criação, do mais recente ao mais antigo

**LIS-0002 - Cenário de teste 2: Ordem cronológica de criação dos cursos na listagem**
- Passo 1: Acessar o link https://creative-sherbet-a51eac.netlify.app/
- Passo 2: Verificar a ordem dos cursos exibidos
- Passo 3: Confirmar que os cursos estão listados em ordem cronológica de criação, do mais recente ao mais antigo

**Caso 3 : Exclusão de um curso**
- Dado que o administrador está na página de listagem de cursos
- E a listagem de cursos já estar pré-populada
- Quando o administrador clica no botão "Excluir curso" de um curso específico
- Então o sistema deve exibir uma mensagem de sucesso: "Curso excluído com sucesso"
- E o curso deve ser removido da listagem

**LIS-0003 - Cenário de teste 3: Exclusão de um curso**
- Passo 1: Acessar o link https://creative-sherbet-a51eac.netlify.app/
- Passo 2: Clicar no botão "Excluir curso" de um curso específico
- Passo 3: Confirmar a exibição da mensagem de sucesso: "Curso excluído com sucesso!"
- Passo 4: Verificar se o curso foi removido da listagem

---
### Documentações: 
[Link para a planilha dos testes](https://docs.google.com/spreadsheets/d/1gAezbh77iSLl894h2c1tTuQt9HH7-ni5z4ZM4YHQ32M/edit?usp=sharing)

[Link para os vídeos de evidências](https://drive.google.com/drive/folders/1DoVO9yYy31PVgmqzOK4Cfn_0SwGj-OL3?usp=sharing)

[Link para a segunda etapa do processo](https://docs.google.com/document/d/1J84v6Glrxh0NggaAwT7I60uFotGRw_0HHh9sugAx3f8/edit?usp=sharing)






