# Contexto de operação (ConOps)
O presente texto fornece uma visão operacional do SISB na perspectiva dos seus usuários. Essa visão é útil para esclarecer alguns dos serviços a serem oferecidos pelo SISB e oferecer orientação para a definição dos [requisitos](https://github.com/kyriosdata/sisb/blob/master/docs/Requisitos.md). 

O presente documento deve, onde aplicável, deve-se observar o conteúdo da ISO 13940, ilustrado no portal [ContSys](https://contsys.org/).

### Contexto do sistema

![sisb-context](https://cloud.githubusercontent.com/assets/1735792/24151701/45197af8-0e28-11e7-804c-86e3577045f9.png)

| Ator           |   Descrição  |
|:--------------:|----------------|
|Administrador   | Responsável pela manutenção do SISB em operação. Alguns serviços permitem ao administrador acompanhar o status da execução do SISB. |
|Odontólogo      | Profissional de saúde que consulta e gera informação em saúde bucal nos prontuários dos pacientes.     |
|Barramento SUS| Barramento com o qual o SISB interage, tanto para enviar quanto para receber informações em conformidade com os padrões adotados pelo Brasil. Alguns dos serviços oferecidos pelo Datasus incluem CNS, CNES, Horus, SIGTAP e eSus-AB, no presente.|

***

## Tempo
O tempo (o momento) em que as informações são capturadas e/ou consultadas é empregado para classificar os requisitos. Boa parte das funções oferecidas pelo SISB, por exemplo, são utilizadas durante a atenção, conforme ilustrada abaixo.

![atencao-bucal](https://cloud.githubusercontent.com/assets/1735792/24455083/b8611ccc-1464-11e7-9577-15f0b5e8cc3b.png)

## Casos de uso

![sisb-use-cases](https://cloud.githubusercontent.com/assets/1735792/23718572/c02b3356-0416-11e7-8617-99558f063784.png)

| Caso de Uso    |   Descrição  |
|--------------|----------------|
|Acrescentar informações| Permite acrescentar informações ao prontuário de um paciente.|
|Consultar informações|Permite consulta às informações contidas em um prontuário de um dado paciente.|
|Localizar paciente| Permite busca por paciente (apenas dados demográficos)|
|Trocar informações| Permite o envio para e o recebimento de informações em saúde contida em sistema externo ao SISB. Em ambos os casos a operação não permite ao usuário o acesso às informações propriamente ditas, mas apenas àquelas pertinentes à transação (transferência).|
|Cadastrar paciente| Dados demográficos de pacientes já cadastrados podem ser confirmados e, se necessário, atualizados, bem como um novo cadastro criado. Permite a recuperação de informações via CNS.|
|Monitorar SISB|Permite acompanhar a operação (funcionamento do SISB).|
|Gerenciar usuários|Permite a gestão do cadastro de usuários do SISB, o que inclui recursos para habilitar/desabilitar usuário, alteração de senha e outras questões pertinentes.|

### Modelo do domínio
Os principais conceitos utilizados pelo SISB são ilustrados abaixo. De forma resumida, um Registro Eletrônico em Saúde (RES), de um dado Paciente, é formado por uma composição de dados em saúde. Cada dado é definido por um arquétipo e, naturalmente, foi produzido por um profissional de saúde (usuário), que possui a devida autorização para tal. As trocas de informação com sistemas externos ou são de importação ou de exportação de dados e, em ambos os casos, está associada a um dado específico.

![sisb-domain](https://cloud.githubusercontent.com/assets/1735792/23722478/436b2994-0424-11e7-872c-1fc261542468.png)

### Visão operacional
Em um cenário típico, por meio da internet tem-se acesso aos recursos oferecidos pelo SISB. Esse acesso é utilizado por odontólogos, pela secretária e também pelo administrador do SISB. Dada a necessidade de manutenção das informações, há previsão de montagem de cópia de segurança, conforme ilustrado abaixo.

![sisb-operacional](https://cloud.githubusercontent.com/assets/1735792/23764690/35f2216e-04dd-11e7-99e8-735665815761.png)

No cenário acima um servidor atende requisições de vários terminais simultanemente. O SISB, contudo, deve ser capaz de operar em outros cenários, por exemplo, no qual o usuário interage com um computador no qual o SISB está em execução, sem conexão com serviço remoto.

### Restrições

- Fazer uso exclusivo de tecnologia "livre" de royalties. 
- O SISB deve apresentar "baixo" custo de implantação e também "baixo" custo de manutenção. O custo deve ser monitorado e, na presença de mudança, aprovado pela patrocinadora do projeto. Naturalmente, o custo é uma função de várias variáveis, inclusive da quantidade de acessos concorrentes por unidade de tempo para os quais o serviço deve se manter estável. 

