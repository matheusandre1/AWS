Anotações e conceitos de cloud.
AWS Cloud Practitioner

Escalabilidade : Aumentar e diminuir o numero de instâncias


Elasticidade : Aumentar/Diminuir os recursos.
Região  
Instância: um recurso de servidor fornecido por serviços de nuvem de terceiros. 

Modelos de recursos:
Modelos
IaaS: infraestrutura como serviço.  ex: EC2.
PaaS: Plataforma como serviço
SaaS: Software como serviço.
Serverless:

Pagamento conforme o uso
Beneficiar-se de economia massiva de escala.
Parar de adivinhar a capacidade
Aumentar a velocidade e a agilidade
Realize economia de custos
Obtenha alcance global em minutos

palavras-chaves: save money,stop guessing, variable expenses, economies of scale,increase speed and agility,Go Global.


Computação Em Nuvem: É a entrega sob demanda de recursos computacionais, através de uma plataforma de serviços via Internet, sem o gerenciamento ativo do usuário.

Usuários: possuem credenciais permanentes, funções possuem credenciais temporarias.
Use o least privilege principle nos usuários
documentos json definem as permissões de acesso.
grupos contém outros usuários, mas não pódem contar outros grupos.

Região é a disponibilização de uma coleção de recursos aws em uma localização geográfica, sendo ele composto por um conjunto de zonas de disponibilidade.

Zona de disponibilidade é um conjunto de datacenters que estão na mesma região, porém separados por um distância significativa, atuando de forma independente em caso de falha de uma zona.

Ponto de presença é uma infraestrutura de servidores localizado próximo de uma ZD, que armazena os dados solicitados no cache, para entregar menor latência uma requisição de consulta.

#Cada Região possui uma ou mais zona de disponibilidade.

#Zona de disponibilidade  estão distintos a quilometros de distância uma das  outras,  conectadas com alta velocidade com segurança local, refrigeração  e podem ser um ou mais data centers.

#Pops serve como cache de dados com menor latência.


#Serviços Regionais: Ec2, lambda,Auto scaling, Beanstalk.

#Serviçõs Globais: Amazon Cloud front, route63, AWF, IAM.

responsabilidade in Cloud: Customer
                 of Cloud: Aws.


armazenamento = buckets
arquivos = objetos
sub-pastas = prefixos


User = Pessoa ou serviço, com credenciais permanentes.
Grupos = Coletivo de Usuários.    grupo contém usuários , não outros grupos.
Funções = Metodo de autentificação temporária.

#AWS WAF = é um firewall de aplicativos web que permite trafégo tem seu acesso permitido ou bloqueado. Mediante a definição de regras personalizáveis.

Camada 7 HTTP.
Bloquear Requisições maliciosas como SQL Injection SQLi e cross-site scripting (XSS)

Geo- match (bloqueio paises), size constraints (limitar tamanho das requisições) e rate based-rules( limitar Quantidade De Requisições por segundo).


#AWS SHIELD standard é Gratuito.

#AWS Shield advanced : É pra mitigar Ataques DDos.
24 x7 , Pago, Proteção extra nos serviços, amazon ec2, elastic load balancing, amazon cloud front, aws Global Accelerator e o Route 53.

#Amazon Ec2.
Serviço Web que disponibiliza uma capacidade computacional segura, representado por uma instância redimensionável na Nuvem.
Windows,MACOS, LINUx.
Infra como serviço(IaaS).
Alugar Maquinas Virtuais
Armazenar Dados em volumes Virtuais(EBS)
Distribuir a Carga de Trabalho (ELB)
Escalar o serviço de Acordo com a demanda (ASG)
Cobrança por Hora ou segundo

AMI - Imagem pré Configurada de uma máquina Virtual.


#Amazon ec2 Launch types

sob demanda = alto custo.
Cobrança o que usar.
Cargas de Trabalho de Curto prazo, validar hip[oteses, com picos de utilização imprevisivel, testar e experimentar um ambiente.

instância spots = 90% de desconto, mas são terminadas quando o preço do spot é maior do que vc pode estabeleceu para pagar. Não utilizar em trabalhos criticos e banco de dados, utilizar em emergência em grande capacidade computacional,trabalhos em lotes,Analise de Dados.
instância reservada = 75% de desconto, Capacidade Reservada, Comprometimento de uso da intância por um período 1 a 3 anos, Pagamento Adiantado, Util pra Ambiente de Produção que foi testado e não será modificado, aplicações que precisar de estado constante excelente para banco de dados.

hosts e instância dedicada = serviço exclusivo pra uso, Hardware Dedico, Visibilidades de soquetes,núcleos, id de host, pode ser comprado por demanda de horas. se optar pela instância terá 70% de desconto em comparação por instância por demanda.
util para vincular licenças de software como windows server, SQL Server e SUSe LINUX Enterprise SERVER.

Dica de exame, cenário.
banco de dados = instância reservada
trazer uma licença = host/ instância DediCAda.
teste= sob demanda
computação extra = instância spots

#Amazon Auto Scaling
escalabilidade automatizada
Scale out ( Adcionar instância)
Scale  in  (Remover Instâncias)
Minimo, Desejado , Máximo.

#AWS ELASTIC BEANSTALK

 É um serviço gerenciado, para os desenvolvedores realizarem uma fácil utilização de implantação e escalabilidade de aplicações e serviços web.
 Gerenciado e gratuito.
 Plataforma como serviço.
 Alta Disponibilidade (Multi-az)
 auto Scaling Group.
 Balança de Carga ( Load balancer)
 
 #Aws LAMBA
 
 Permite executar Códigos sem provisionar ou gerenciar servidores, pagando apenas pelo número de solicitações e pelo tempo de computação que você utilizar.
 Serverless
 Dimensiona Aplicação.
 Escalável
 Baixo Custo
 Multiplas Linguagens

 #AWS S3: Storage

Serviço de armazenamento e recuperação de objetos, respondendo com escalabilidade, disponibilidade, segurança e performance.
 Armazenamento Virtual ilimitado
 Compartilha Arquivos ou Criação de um Website Estático
 Armazena snapshots, faz backups e armazenamento hibrido do seu ambiente on-premises
 Repositório de Data Lakes e análises de big Data.
 Baixa Latência e alta velocidade.
 
Armazenamentos == buckets
Arquivos == objetos
sub-pastas == Prefixos
 
URL = ID GLOBAL + SERVIÇO + REGIÃO + DOMINIO + PREFIXO + OBJETO

TAMANHO MÁXIMO OBJETO 5 TB.
UPLOAD > 5 GB USE MULTI PART UPLOAD.
METADATA (CHAVE E VALOR POR SISTEMA E USUÁRIO)
TAGS (CHAVE E VALOR POR USUÁRIO).
VERSIONAMENTO DE OBJETOS.

CLASSES DE ARMAZENAMENTOS DE DIFERENTES CASOS DE USO
CONJUNTO  COM A POLITICA DE CICLO DI VIDA, OS DADOS SÃO MIGRADOS AUTOMATICAMENTO ENTRE ESSAS CATEGORIAS, REFLETINDO EM UM MENOR CUSTO DE ARMAZENAMENTO.

S3 STANDARD = USO GERAL
S3 INTELLIGENT TIERING = USO GERAL E MOVIMENTAÇÃO AUTOMÁTICA
S3 STANDARD IA = MENOR FREQUÊNCIA E IDEAL PARA BACKUP
S3 ONE ZONE IA = MENOR FREQUÊNCIA, MAS SÓ UMA ZONA DE DISPONIBILIDADE
S3 GLACIER = ARQUIVAR DADOS
S3 GLACIER DEEP ARCHIVE = RETENÇÃO LONGO PRAZO > 7 ANOS.

#Amazon EBS ELASTIC BLOCK STORE

ARMAZENAMENTO DE BLOCOS EM ALTA ESCALA FÁCIL DE USAR EM QUALQUER ESCALA

SERVIÇO DE BLOCOS PERSISTENTES, PROJETADO COMO UM VOLUME, PARA SER CONECTADO E UTILIZADO COMO UM DISCO, EM INSTÂNCIAS DO AMAZON EC2.

BLOCOS PERSISTENTES
PROTEÇÃO ATRAVÉS DE REPLICAÇÃO
DIFERENTES TIPOS DE DISCOS (SSD E HDD).
REDIMENSIONAR EM MINUTOS (ON THE FLY)
PAGAR POR AQUILO QUE ESTÁ SENDO PROVISIONADO.
SNAPSHOTS MANUAL OU AUTOMÁTICO (POINT IN TIME)
CRIPTOGRAFIA EM REPOUSO.
UMA ZONA DE DISPONIBILIDADE.

FAMILIA AWS SNOW

Snowcone ==== Snowball --- Snowmobile

Snowcone

8TB
2vCPU
4GB memória 
Criptogra em 256 bits
para funções administrativas

Manipular Dados em eventos esportivos
Missõs do Exército

poder computacional de banco de dados num Hospital de Campanha 

AWS Snowcone dentro dele, e depois retorna pra AWS.

#SNOWBALL EDGE

Duas ramificações:
#Storage optimized: importar e exportar dados na nuvem AWS.
100 TB (Disponivel 80TB)
24 vCPU
32 GB memória

#Compute Optimized : Otimizado pra computacional, poder computacional
42 TB (Disponivel 39,5 TB)
52 vCPU
208 GB memória
SSD 7.68 TB NVMe

Criptografia em 256 bits
Resistente a Violações.

Transportes de dados em EScala: Petabytes.


#SNOWMOBILE

Pode Transportar até 100 petabytes de dados em uma única viagem, o equivalente a usar 1.250 dispositivos AWS Snowball.

Migração Exabytes


S3 Glacier Deep Archive = manter o armazenamento por um longo prazo.

classes de armazenamento de objetos de longe prazo, seguras e resilientes do amazon.
 
Glacier
DEEP Archive

Disponibilidade de 99,99%

Durabilidade anual média ==

Dados armazenados como arquivos
Conteúdo imutavel após p envio.

Recuperação Padrão 3 a 5 h

Recuperação MASSa  5 a 12h

Recuperação Expressa (<250mb)  1 a 5 m

Dados recuperados ficam no bucket s3 por 24 horas.

#Amazon VPC é um sessão de rede isolada logicamente na nuvem AWS, que permite custommizar uma rede virtual e executar recursos em um ambiente com controle total.
Mesmo conceito on -premisses.

Camadas de segurança

Conectividade com outros serviços, Podendo fazer integração

Divido em uma Região e Zonas Disponibilidades
Sub-redes Públicas : Tem acesso a Internet.
Privadas: 
Tabela de Roteamento
internet Gateway Sub-rede pública : serviço que dá acesso a internet.
Nat Gateway Sub-rede Privada: é o serviço que concede acesso a sub-rede privada. 
Security Group[SG] = Firewall atua na instância.
Network Access List [NACLS] = firewall opcional, atua no nivel da sub-rede.

Tabela de roteamento faz  a comunicação sub-redes e as instâncias.

#Amazon Route 53 = Serviço que Mexe com DNS

Encaminha as solicitações dos usuários. para os aplicativos de internet.

o nome Route 53 é um referência da Porta 53.

Gerenciamento de DNS.

Conjunto de regras e registros que ajudam o cliente a chegar ao destino através de uma URL 

Registros Comuns 

Registro A: ex: www.google.com/  registro IP. /IVP4

Registro AAAA 0:0:0:0:0:ffff:d8ef:2678 / IPV6

Registro CNAME: nome da url / Hostname para Hostname

Registro ALias : Recurso Aws / ELB, CLOUDFRONT, S3,RDS e etc.

Registro de Trafégo

Simples, sem health check
Geolocalização, mais proximo da região.
FaiLover, Possui
Ponderado, não tbm possui
latência possui health check
Valores Múltiplos até 8 registros íntegros.

Monitoramento Disponibilidade.
Registros de Dominios

#Amazon CloudFront = Serviço de entrega de conteúdo CDN, entrega dados, videos,aplicativos e apis a cliente de forma mundial, com segurança, baixa latência e Alta velocidade.

Pontos de Presença

Elastic LOAD BALANCER

distribuir automaticamento o tráfego de entrada de aplicativos entre diversos destinos, como instâncias do amazon ec2, Contêineres,endereços ip e funções lambda.

Application Load Balancer = Protocolos Http, Https, Plataforma VPC, Camada 7.

Network = Protocolos TCP, UDP, TLS, amazon vpc, CAMada 4, EC2, microserviços, conteineres
Gateway = Camada 3, ip , VPC Gerenciar Appliance, inspeção de pacotes, no amazon ec2.
CLassic

#Amazon CloudWatch

serviço de monitoramento de desempenho dos recursos e dos aplicativos que você executa no seu ambiente.

Coletar 

Monitorar

atuar

analisar

#AWS CLoudTrail
Possibilita Governança, conformidade, Auditoria Operacional e auditoria de riscos em sua conta aws.

CLoudwatch = perfomance, desempenho

CLoudtrail = auditoria, conformidade.
 

#AWS Config

serviço que permite acessar,auditar e avaliar as configurações dos recursos da aws.

regional

Auxilia na auditoria das alterações dos recursos para compliance

Mantém histórico das alterações e armazena em um bucket s3 para posterior análise

Notificações de alterações são enviadas com o amazon sns e disponibilizadas no dashboad do AWS Config.

#AWS ORGANIZATIONS

Permite que você gerencie e controle seu ambiente de maneira centralizada.

Consolidar Faturamento
Agregar preços
Gerar economia com pooling de instâncias reservadas

Serviço global
Permite gerenciar múltiplas contas aws.

Uma conta principal Master account.
API disponivel para criação de contas.
restrição das contas usando scp.

#WELL-ARCHITECTED

Pare, Teste, Automatize, Permita, Contrua, Melhore.

Principios de design:

Escalabilidade : Vertical e Horizontal
Recursos Descartáveis: nada é para sempre.
Automação: Serverless, Iaas, autoscaling.
Loose couple: falhas não podem cascatear e não ao monolíto.
Serviços não Servidores

Cinco pilares 

Operational Excellence
Security
Rebiability
Performance Efficiency
Cost Optimization

#AWS ARTIFACT
acordos e relatórios de conformidade

documentos são chamados de artefatos
Os relatórios de seguranç e compliance são iso,pci e soc.
Os acordos de uso de serviços,(Agreements), São BAA e HIPAA.

#AWs trusted Advisor

ferramenta que oferece orientação em :
Otimização de custo
Desempenho
Segurança
tolerância a Falhas
Limites De Serviço

#AMAZON RDS - banco relacional

Destaca-se por sua escalabilidade,automatização na aplicação de patches,provisionamento de hardware e backup na Nuvem AWs.

Amazon aurora
Mysql
mariaDB
postgreeSQL
oracle
MySQL Server

Multi-az - Simples,Segura,Funcional.

outra zona de disponibilidade
redundância de dados
eliminar congelamento
minimizar picos
alta disponibilidade

#Amazon DinamoDB NOSQL de valor-chave e documento que oferece desempenho.

Serverless
escalável
Confiável
rápido.

chave primária pode ser simples ou composta.

tabela == coleção de itens
cada item possui um atributo
chave primária é obrigatória e é utilizada para identificar um item na tabela.

chave segundária é opcional.

#AWS CLoudFormation
Serviço que oferece uma linguagem comum para que você possa descrever e fornecer todos os recursos de infra em ambiente de nuvem.

replicar infraestrutura multipla vezes
time de desenvolvimento usar como ambiente de testes de produção
precisa ter controle de versão.
aws = IAC



Total controle na configuração.
 

3306 porta de mysql