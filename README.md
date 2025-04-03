# pilha-e-fila
#Atividade: Utilizar um código de pilha o fila em uma situação real

# Classe para representar o painel de atendimento usando Fila
class AtendimentoFila:
    def _init_(self):
        self.queue = PersonalQueue()  # Usamos a fila personalizada definida no código anterior
    
    # Função para adicionar um cliente à fila
    def adicionar_cliente(self, nome_cliente):
        print(f"Cliente {nome_cliente} entrou na fila.")
        self.queue.enqueue(nome_cliente)
    
    # Função para atender o próximo cliente da fila
    def atender_cliente(self):
        cliente_atendido = self.queue.dequeue()
        if cliente_atendido:
            print(f"Atendendo cliente: {cliente_atendido}")
        else:
            print("Não há clientes na fila para atender.")
    
    # Função para ver o próximo cliente que será atendido (sem remover)
    def proximo_cliente(self):
        cliente = self.queue.list.elementAt(0)
        if cliente:
            print(f"O próximo cliente a ser atendido é: {cliente}")
        else:
            print("Não há próximos clientes na fila.")
    
    # Função para mostrar todos os clientes na fila
    def listar_fila(self):
        if self.queue.list.size() > 0:
            print("Clientes na fila: ", end="")
            for i in range(self.queue.list.size()):
                print(self.queue.list.elementAt(i), end=" ")
            print()
        else:
            print("A fila está vazia.")

# Criação do sistema de painel de atendimento
painel_atendimento = AtendimentoFila()

# Adicionando clientes à fila
painel_atendimento.adicionar_cliente("Cliente A")
painel_atendimento.adicionar_cliente("Cliente B")
painel_atendimento.adicionar_cliente("Cliente C")
painel_atendimento.adicionar_cliente("Cliente D")
painel_atendimento.adicionar_cliente("Cliente E")

# Listando os clientes na fila
painel_atendimento.listar_fila()

# Atendendo alguns clientes
painel_atendimento.atender_cliente()  # Atende o primeiro da fila
painel_atendimento.atender_cliente()  # Atende o próximo

# Mostrando quem será o próximo cliente a ser atendido
painel_atendimento.proximo_cliente()

# Listando novamente os clientes na fila
painel_atendimento.listar_fila()

# Atendendo os restantes dos clientes
painel_atendimento.atender_cliente()
painel_atendimento.atender_cliente()
painel_atendimento.atender_cliente()
painel_atendimento.atender_cliente()  # Verifica se há mais clientes
