# resumo-do-lab-azure
Resumo sobre SLA do Azure
O Service Level Agreement (SLA) do Azure define os níveis de serviço que a Microsoft garante para os seus serviços na nuvem. Para máquinas virtuais (VMs), o Azure oferece diferentes níveis de SLA com base na arquitetura de alta disponibilidade e resiliência. Por exemplo:

SLA de uma única VM: A disponibilidade garantida é de 99,9% se a VM estiver usando discos gerenciados.
SLA de VMs em Conjuntos de Disponibilidade (Availability Sets): A disponibilidade aumenta para 99,95% quando as VMs são distribuídas entre domínios de falha e atualização.
SLA para VMs em Zonas de Disponibilidade (Availability Zones): Oferece uma garantia de 99,99%, distribuindo as VMs entre diferentes zonas dentro da mesma região.
Criação de VMs em Zonas de Disponibilidade
As Zonas de Disponibilidade são zonas físicas separadas dentro de uma região do Azure, cada uma com seu próprio datacenter independente. Ao criar VMs em zonas de disponibilidade diferentes, você aumenta a resiliência contra falhas de datacenter, já que cada zona possui alimentação, rede e refrigeração independentes.

Vantagem de usar múltiplas zonas: Se uma zona falhar, as VMs nas outras zonas continuarão funcionando. Isso melhora a continuidade de serviços críticos.
Recomendação: Distribuir suas VMs em pelo menos duas zonas para aumentar a disponibilidade e resiliência da aplicação.
Estratégia com VMSS (Virtual Machine Scale Sets) para três zonas
Se você deseja criar VMs em três zonas de disponibilidade diferentes, uma estratégia mais eficiente pode ser o uso de VMSS (Virtual Machine Scale Sets). O VMSS permite que você escale automaticamente as VMs de forma horizontal (aumentando ou diminuindo o número de instâncias) e distribua essas VMs entre várias zonas de disponibilidade. Isso garante alta disponibilidade e escalabilidade automatizada.

Benefícios do VMSS:
Distribuição automática das VMs em zonas de disponibilidade diferentes.
Gerenciamento centralizado de todas as instâncias de VMs.
Escalonamento automático baseado na demanda de tráfego ou carga de trabalho.
Armazenamento de VMs e Redundância
O armazenamento das VMs no Azure é baseado em Discos Gerenciados. Esses discos são altamente duráveis e oferecem várias opções de redundância para garantir que os dados sejam preservados em caso de falha em um datacenter ou zona.

Tipos de Redundância de Armazenamento:
Locally Redundant Storage (LRS): Mantém três cópias dos dados dentro de um único datacenter, oferecendo proteção contra falhas de hardware.
Zone-Redundant Storage (ZRS): Replica os dados entre três zonas de disponibilidade diferentes dentro da mesma região, garantindo alta durabilidade e proteção contra falhas de zonas inteiras.
Geo-Redundant Storage (GRS): Replica os dados em uma região secundária distante, oferecendo recuperação em caso de desastres regionais.
Para cenários de alta disponibilidade, é recomendável usar ZRS para garantir que os dados de uma VM estejam sempre acessíveis, mesmo em caso de falha de uma zona.

Conclusão
Ao planejar a implantação de VMs no Azure, considere a estratégia de disponibilidade com base no SLA desejado. Distribuir as VMs em zonas de disponibilidade aumenta a resiliência, e o uso de VMSS pode automatizar a distribuição em várias zonas. Por fim, para garantir a integridade dos dados, escolha a opção de armazenamento redundante que melhor se adapta às necessidades de continuidade e recuperação de desastres.
