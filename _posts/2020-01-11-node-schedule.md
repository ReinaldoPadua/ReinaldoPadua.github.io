---
title: 'Agendamento de tarefas com node-schedule'
---

Em um projeto particular que tenho trabalhado com framework express, um recurso
que eu precisei desenvolver foi a chamada periodica de uma determinada api. Essa
api deveria ser chamada multiplas vezes, em periodos distintos, com parametros diferentes.

Dada a complexidade, usar um agendador de tarefas como o crontab demandaria de muito esforço, em função disso optei por usar a lib [node-schedule](https://github.com/node-schedule/node-schedule).

Seu uso é demasiadamente simples, bastando executar a instalação via npm install, e após e importar a lib via require. A definição de peridiocidade vai ser bem semelhamente a configuração
da crontab de sistemas Linux, seguindo padrão de configuração segundo - minuto- hora- dia do mês - mês - dia da semana.

Segue alguns exemplos:

```
npm install node-schedule //instalação da lib.
```

```
// importa da lib.
const schedule = require('node-schedule');

schedule.scheduleJob('5 * * * * *', (){
  console.log('A tarefa vai ser executada no segundo "5" de cada minuto.');
});

schedule.scheduleJob('*/5 * * * * *', (){
  console.log('A tarefa vai ser executada a cada 5 segundos.');
});

schedule.scheduleJob('42 * * * *', (){
  console.log('A tarefa vai ser executada no minuto 42 de cada hora.');
});
```

A implementação na prática pode ser vista no projeot [node-schedule-jobs](https://github.com/ReinaldoPadua/node-schedule-jobs).

Até a próxima.
