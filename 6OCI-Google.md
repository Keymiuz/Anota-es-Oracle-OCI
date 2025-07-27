# Oracle Interconnect for Google Cloud

## O que é o Oracle Interconnect for Google Cloud?

É uma parceria entre a Oracle e o Google que cria uma experiência de nuvem integrada, utilizando **OCI FastConnect** e **Google Cloud Interconnect** para estabelecer uma conexão de rede privada, dedicada e de baixa latência entre as duas nuvens.

* **Conexão Direta:** A conectividade física é estabelecida diretamente entre os serviços FastConnect e Interconnect, **sem um provedor de serviço intermediário**.
* **Disponibilidade:** Lançado em 11 regiões comerciais globais, com pareamento específico entre regiões OCI e GCP.

## Principais Benefícios

* **Conectividade Dedicada e Rápida:**
    * Como a conexão física já existe, os circuitos virtuais podem ser provisionados em minutos.
    * A largura de banda pode ser modificada conforme a necessidade, e múltiplos circuitos podem ser configurados para roteamento **ECMP (Equal Cost Multi-Path)**.
* **Sem Custos de Transferência de Dados:**
    * Você **não paga** por transferência de dados (entrada ou saída) através da interconexão.
    * Os únicos custos são as taxas de porta de cada nuvem (FastConnect no OCI e Interconnect no GCP).
* **Modelo de Suporte Colaborativo:**
    * Você pode abrir um chamado de suporte com a Oracle (My Oracle Support) ou com o Google Cloud Support.
    * As equipes de suporte de ambas as empresas se engajam diretamente para resolver os problemas dos clientes rapidamente.

## Arquitetura da Conexão

| Componente | Oracle Cloud Infrastructure (OCI) | Google Cloud Platform (GCP) |
| :--- | :--- | :--- |
| **Rede Virtual** | Virtual Cloud Network (VCN) | Virtual Private Cloud (VPC) |
| **Gateway** | Dynamic Routing Gateway (DRG) | Google Cloud Router |
| **Circuito Virtual**| FastConnect (usando o tipo **Partner**) | Partner Interconnect (VLAN attachment) |

## Padrões de Arquitetura Comuns

1.  **Google Cloud como Rede de Trânsito:**
    * Você pode usar sua conexão existente com o Google Cloud (seja via Interconnect ou Cloud VPN a partir do seu on-premises) para estender a conectividade até o OCI, usando o GCP como uma rede de passagem.

2.  **Estender Conectividade para Outras Regiões OCI:**
    * Se você precisa de conectividade do GCP para uma região do OCI onde a interconexão direta ainda não está disponível, você pode:
        1.  Conectar-se à região OCI pareada.
        2.  Usar um **Remote Peering Connection** entre os DRGs para alcançar a outra região do OCI.

## Processo de Configuração

O processo envolve ações em ambos os consoles. A chave para a conexão é a troca de uma **"Pairing Key"**.

1.  **No OCI:** Crie um DRG e anexe-o à sua VCN.
2.  **No GCP:** Crie um Google Cloud Router.
3.  **No GCP:** Crie um **VLAN attachment** do tipo **Partner Interconnect**. Este passo irá gerar uma **Pairing Key**. Copie esta chave.
4.  **No OCI:** Crie uma conexão **FastConnect** do tipo **Partner**, selecionando "Google Cloud / OCI Interconnect". Cole a **Pairing Key** obtida do GCP no campo "Partner Service Key".
5.  **Verificação:** Confirme que os circuitos estão provisionados e ativos em ambos os lados.
6.  **Configuração Final:** Configure as **regras de segurança** e as **tabelas de rota** em ambas as nuvens para permitir e direcionar o tráfego.
7.  **Teste:** Teste a conectividade entre as instâncias.

## Resiliência

Para obter resiliência, você pode repetir todo o processo para criar uma **segunda conexão** FastConnect Partner entre o OCI e o Google Cloud.