# Benchmark de Criptografia em Máquinas Virtuais

Programa de linha de comando para medir o desempenho de operações criptográficas em máquinas virtuais com diferentes quantidades de CPUs e memória. O repositório também armazena planilhas XLSX produzidas durante os experimentos.

Repositório: [KaykyCrespo/INICIACAO_CIENTIFICA-Analise-de-desempenho-em-VM-S-comparando-a-criptografia-RSA](https://github.com/KaykyCrespo/INICIACAO_CIENTIFICA-Analise-de-desempenho-em-VM-S-comparando-a-criptografia-RSA)

## Funcionalidades

- Executa benchmarks de Ed25519 e X25519.
- Executa benchmarks de ECDSA e ECDH com as curvas NIST P-256, P-384 e P-521.
- Executa benchmarks RSA com chaves de 1024, 2048 e 4096 bits.
- Mede tempo de execução, variação de memória do processo e uso de CPU.
- Permite exportar os resultados da sessão em CSV ou XLSX.
- Inclui planilhas XLSX de execuções anteriores em seis configurações de VM.

## Tecnologias

- Python 3
- [cryptography](https://cryptography.io/): primitivas e algoritmos criptográficos.
- [psutil](https://psutil.readthedocs.io/): informações de CPU, memória e processos.
- [openpyxl](https://openpyxl.readthedocs.io/): exportação de planilhas XLSX.

## Requisitos e execução

Use Python 3 e, para reproduzir os experimentos, uma máquina virtual cuja quantidade de CPUs e memória tenha sido configurada no hipervisor. No terminal, na pasta do projeto, instale as dependências:

```bash
python -m pip install cryptography psutil openpyxl
```

Inicie o menu interativo com:

```bash
python BenchMarck.py
```

No menu, escolha um grupo de algoritmos ou a opção de benchmark completo. Os resultados podem ser exportados pelas opções CSV e XLSX. Os arquivos exportados são criados no diretório de onde o programa foi iniciado.

## Estrutura

```text
.
|-- BenchMarck.py       # Aplicação e implementação dos benchmarks
|-- LICENSE             # Licença MIT
|-- README.md           # Documentacao do projeto
|-- 2CPU_0.5GB/         # Planilhas: VM com 2 CPUs e aproximadamente 0,5 GB
|-- 2CPU_1.0GB/         # Planilhas: VM com 2 CPUs e aproximadamente 1,0 GB
|-- 4CPU_0.5GB/         # Planilhas: VM com 4 CPUs e aproximadamente 0,5 GB
|-- 4CPU_1.0GB/         # Planilhas: VM com 4 CPUs e aproximadamente 1,0 GB
|-- 6CPU_0.5GB/         # Planilhas: VM com 6 CPUs e aproximadamente 0,5 GB
`-- 6CPU_1.0GB/         # Planilhas: VM com 6 CPUs e aproximadamente 1,0 GB
```

Cada pasta de configuração contém planilhas XLSX de execuções anteriores. Os nomes dos arquivos registram a quantidade de CPUs, a memória detectada e a data e hora da exportação.

## Observações sobre os experimentos

- Configure CPUs e memória da VM no hipervisor antes de executar o programa. A opção de configuração do menu não limita efetivamente os recursos do sistema operacional; os valores escolhidos servem como parâmetros informativos do programa e dos arquivos exportados.
- Os resultados dependem do sistema operacional, do hipervisor, da carga da máquina e das versões das bibliotecas. Compare execuções feitas em condições equivalentes.
- As planilhas são resultados brutos de execuções individuais, não uma análise estatística consolidada. Não interprete uma única execução como conclusão geral sobre um algoritmo.
- As versões exatas das dependências usadas para gerar as planilhas existentes não estão registradas neste repositório.

## Autoria e licenca

Autoria indicada no arquivo de licença: Kayky Crespo dos Santos. O projeto está sob a licença MIT; consulte [LICENSE](LICENSE).
