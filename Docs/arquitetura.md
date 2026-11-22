# Descrição de arquitetura do tanque de piscicultura — segundo a ISO/IEC/IEEE 42010

A ISO/IEC/IEEE 42010:2022 não
manda desenhar um diagrama específico: manda dizer **para quem** a arquitetura é descrita, **que
preocupações** cada interessado tem, **de que pontos de vista** o sistema será olhado para responder
a elas, e então apresentar as **vistas**, as **correspondências** entre elas e as **decisões** com as
suas justificativas. A ISO/IEC 30141:2024, a arquitetura de referência de IoT, é organizada
exatamente assim — e os pontos de vista abaixo vêm dela.


## 1. Entidade de interesse

O sistema de monitoramento, controle e gêmeo digital de um tanque circular de lona para piscicultura, com diâmetro de 4 metros e 1,20 metros de altura. 

O que permanece dentro do escopo é o monitoramento das condições da água, identificação de condições inadequadas, controle de aerador, controle de bomba de renovação de água, alimentação automatizada, registro de eventos, representação digital do tanque e alertas ao produtor.

Fora do escopo: compra de insumos, gestão financeira, rede elétrica, reconhecimento e gestão de peixes dentro do tanque (isso é, tempo de engorda, população por m³ etc).

## 2. Interessados e preocupações

| ID | Interessado | Preocupação |
|---|---|---|
| P1 | Piscicultor | Saber antecipadamente se a água apresenta condições inadequadas para a criação dos peixes |
| P2 | Piscicultor | Saber quando é necessário alimentar os peixes, renovar a água ou realizar alguma intervenção |
| P3 | Técnico de aquicultura | Saber se os dados dos sensores são confiáveis e se os parâmetros utilizados são adequados à espécie cultivada. |
| P4 | Técnico de manutenção | Trocar um sensor ou o nó sem parar o resto e sem reprogramar a plataforma |
| P5 | Integrador | Adicionar novos sensores, atuadores ou tanques sem precisar modificar toda a arquitetura |
| P6 | Todos | O que acontece com o tanque quando a internet ou a rede local cai? |
| P7 | Piscicultor e integrador | Quem pode consultar as informações e quem pode comandar os atuadores remotamente? |
| P8 | Piscicultor | Quanto custa manter o sistema funcionando, considerando energia, conectividade e manutenção? |


## 3. Pontos de vista adotados

| Ponto de vista (ISO/IEC 30141) | Preocupações que responde | Tipos de modelo usados |
|---|---|---|
| Uso | P1, P2, P8 | tabela de casos de uso com frequência e prazo |
| Funcional | P1, P3, P5 | diagrama de componentes por domínio; fluxos de dados |
| Construção (implantação) | P4, P6 | diagrama de implantação: nós, redes, portas |
| Confiança (*trustworthiness*) | P6, P7 | modelo de ameaças STRIDE (Aula 10); disponibilidade da cadeia (Aula 6) |

## 4. Vista de uso

| Caso de uso | Ator | Frequência | Prazo aceitável |
|---|---|---|---|
Acompanhar as condições da água no painel |	Piscicultor	| Algumas vezes ao dia	| Segundos
Receber alertas de oxigênio baixo, pH inadequado ou temperatura fora dos limites |	Piscicultor |	Quando acontece	| Segundos 
Consultar o histórico das condições da água	| Piscicultor, técnico em aquicultura |	Diária ou semanal |	Segundos
Verificar o estado dos equipamentos (bombas, aerador e alimentador)	| Piscicultor |	Algumas vezes ao dia |	Segundos
Programar e acompanhar a alimentação dos peixes |	Piscicultor	| Diária |	Minutos
Comandar bomba e aerador remotamente |	Piscicultor |	Eventual |	Segundos
Analisar as condições do cultivo e identificar tendências |	Técnico em aquicultura |	Semanal	 | Minutos
Identificar falhas de sensores e dispositivos |	Técnico de manutenção |	Quando acontece |	Minutos
Consultar o estado de conectividade e funcionamento do sistema |	Técnico de manutenção, integrador	| Eventual ou quando acontece |	Minutos

## 5. Vista funcional

## 6. Vista de implantação

## 7. Vista de confiança

## 8. Correspondências entre as vistas

## 9. Decisões e justificativas

## 10. Questões em aberto