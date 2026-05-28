---

## Projetos

### 1. Simulador de Firewall
Simula o funcionamento de um firewall básico. Gera IPs aleatórios e os compara com uma lista de bloqueio predefinida, imprimindo a ação tomada (allow/block) para cada pacote.

**Conceitos praticados:** dicionários, funções, f-strings, módulo `random`

```python
# Exemplo de saída
IP: 192.168.1.9,  Action: block,  Random: 4821
IP: 192.168.1.3,  Action: allow,  Random: 0293
IP: 192.168.1.13, Action: block,  Random: 7754
```

---

### 2. Bloqueador de Ataques DoS
Monitora o tráfego de rede em tempo real usando a biblioteca **Scapy**. Se um IP ultrapassar 40 pacotes/segundo, ele é automaticamente bloqueado via `iptables`.

**Conceitos praticados:** Scapy, `defaultdict`, `os.system`, monitoramento de rede, privilégios de root

```python
# Exemplo de saída
Monitorando o tráfego...
blocking IP: 192.168.1.105, packet rate: 87.4
blocking IP: 10.0.0.23,     packet rate: 134.2
```

> Requer execução como root no Linux: `sudo python3 dos_blocker.py`

---

## Requisitos

- Python 3.10+
- Linux (para o bloqueador de DoS)
- Scapy

```bash
pip install scapy
```

---

## Como Executar

```bash
# Simulador de Firewall
python3 firewall_simulator/firewall.py

# Bloqueador de DoS (requer root)
sudo python3 dos_blocker/dos_blocker.py

# Verificar IPs bloqueados
iptables -L

# Desbloquear um IP manualmente
iptables -D INPUT -s <IP> -j DROP
```

---

## O que estou aprendendo

- Lógica de firewall e regras de filtragem de pacotes
- Captura e análise de tráfego de rede com Scapy
- Estruturas de dados do Python aplicadas à segurança (`defaultdict`, `set`)
- Simulação de ataques DoS em ambiente controlado
- Uso de `iptables` via Python para bloqueio dinâmico de IPs

---

## Aviso Legal

Todos os scripts deste repositório são para fins exclusivamente educacionais.
Usar essas ferramentas em redes que não são suas é ilegal. Teste apenas em ambientes controlados ou na sua própria rede.

---

## Autor

Estudante de Cibersegurança — em formação
