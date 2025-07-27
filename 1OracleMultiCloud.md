# Arquiteto Multicloud OCI


## Introdução e Definição de Multicloud

### O que é Multicloud?
É o uso coordenado de serviços em nuvem de mais de um provedor de serviços em nuvem (dois ou mais).

### Por que usar Multicloud?
Existem várias razões para um cliente querer utilizar múltiplos provedores de nuvem:

* **Evitar Vendor Lock-in:** Mitigar ou evitar a dependência de um único fornecedor.
* **Best-of-Breed:** Utilizar o melhor produto de cada provedor de nuvem, criando uma solução combinada e otimizada.
* **Otimização de Custos:** Buscar as melhores condições de preço entre os provedores.
* **Outros Drivers:** Redundância, conformidade regulatória, etc.


## Multicloud é o Novo Normal

A Oracle é uma das primeiras a adotar e é pioneira em serviços multicloud, pois essa é a realidade do mercado atual.

### Dados do Mercado:
* **Estudo da Flexera:** 89% das empresas utilizam uma estratégia multicloud.
* **Estudo da Oracle:** Mais de 90% dos clientes usam dois ou mais provedores de nuvem.
* **Estudo da HashiCorp:** 94% das empresas afirmam que a estratégia multicloud ajudou a avançar seus objetivos de negócio.

### Principais Motivadores (Drivers) para o Multicloud
* **Redundância:** Se um provedor de nuvem falhar, o outro mantém a operação da organização funcionando.
* **Conformidade Regulatória e Soberania de Dados:** Manter os dados dentro de uma região geográfica específica, seja por mandatos governamentais ou como um valor agregado para os clientes.

## Ofertas Multicloud e Híbridas da Oracle

### 1. Parceria com Microsoft Azure
* **Interconexão OCI-Azure (desde 2019):** Conexão direta de baixa latência (**Oracle FastConnect** para **Azure ExpressRoute**).
* **Oracle Database Service@Azure:** Serviço de banco de dados Oracle rodando diretamente nos datacenters do Azure.

### 2. Cloud Híbrida (Cloud no seu Data Center)
* **Oracle Exadata Cloud@Customer:** Leve um rack inteiro, meio rack ou um quarto de rack para o seu data center.
* **Oracle Roving Edge:** Solução para borda da nuvem.

### 3. Nuvem Pública e Regiões Dedicadas
* **Nuvem Pública:** Mais de 45 regiões comerciais e governamentais (EUA, Reino Unido, UE).
* **Dedicated Region Cloud@Customer:** Uma região inteira da OCI, com mais de 100 serviços, implementada atrás do seu firewall.


## Detalhes da Interconexão OCI e Azure

* **Proximidade:** 12 das 48 regiões da Oracle já estão interconectadas com o Azure, localizadas no mesmo datacenter ou muito próximas.
* **Configuração:** A configuração da interconexão é simples e será demonstrada em lições futuras.
* **Benefícios:**
    * Baixa latência, alta taxa de transferência e desempenho previsível.
    * **Sem custos de egresso (saída de dados)** do lado do OCI para essa conexão.

## Detalhes do Oracle Database@Azure

Este serviço entrega os serviços de banco de dados Oracle dentro dos datacenters do Microsoft Azure.

### Principais Benefícios:
* **Co-localização com o Azure:** Oferece integração nativa, eliminando a necessidade de configuração manual de interconexão.
* **Latência de Microssegundos** entre as aplicações no Azure e o banco de dados Oracle.
* **Disponibilidade do OCI Native Exadata Database Service**, garantindo o mais alto nível de desempenho, escalabilidade e segurança.
* **Suporte técnico unificado**, que pode ser fornecido tanto pela Microsoft quanto pela Oracle.

