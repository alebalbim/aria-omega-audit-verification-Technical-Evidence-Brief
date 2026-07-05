# 🔐 ARIA OMEGA · Glass Box Auditability Verification

**Technical Evidence Brief · Comprovação Técnica de Auditabilidade**

---

## 📌 Visão Geral

Este repositório contém evidências verificáveis independentemente da auditabilidade **Glass Box** (ante-hoc) na arquitetura meta-cognitiva **ARIA OMEGA (ADCW-O)**, incluindo:

- ✅ Provas criptográficas de integridade (SHA-256 · RSA-2048)
- ✅ Dados de convergência do Brier Score (Protocol 3.2, N=142)
- ✅ Pacote completo de artefatos comprobatórios com AUDIT-SEAL
- ✅ Validação de auditabilidade causal por inferência individual

---

## 🎯 Métricas-Chave de Validação

| Métrica | Valor | Descrição |
|---------|-------|-----------|
| **Brier Score Inicial** | 0.190 | Q1 — Maior incerteza no início do teste |
| **Brier Score Final** | 0.040 | Q18 — Calibração convergida (−79%) |
| **Brier Score Médio** | 0.113 | Média das 18 questões auditadas |
| **Melhoria Total** | Δ = −0.150 | Convergência de calibração Q1→Q18 |
| **Threshold Glass Box** | 0.150 | Limiar de aceitação |
| **Questões Aprovadas** | 12/18 | Q7–Q18 abaixo do threshold |
| **Dataset** | N=142 | Tamanho do dataset de calibração |
| **Execução** | T=0 · S=42 | Determinística e totalmente reproduzível |

---

## 📐 Arquitetura ADCW-O

O protocolo **ADCW-O** impõe um pipeline tripartite obrigatório antes de qualquer output:

### **Layer 1 · MIT_OMEGA**
- Interpretabilidade causal
- DAGs causais (Pearl SCM)
- Certeza [0.0–1.0]
- Source Attribution

### **Layer 2 · GRO (Membrana de Risco)**
- Premissas rejeitadas
- Cenários probabilísticos
- Brier Score
- Decomposição de opacidade

### **Layer 3 · X_CAUSAL**
- Verdade soberana
- CAUSA → MECANISMO → EFEITO → JANELA
- Rastreabilidade causal completa

### **Output + Audit Block**
- [ARIA-OMEGA-AUDIT-BLOCK] auto-gerado
- SHA-256 · RSA-2048
- Audit Trail Hash
- AUDIT-SEAL

---

## 🔐 Validação Criptográfica

Todos os artefatos são **publicamente verificáveis** sem intermediários. Qualquer auditor pode verificar a integridade criptográfica usando:

```bash
# Verificar hash SHA-256
sha256sum bundle.tar

# Verificar assinatura RSA-2048
openssl dgst -sha256 -verify public.pem -signature signature.bin bundle.tar
```

### **Artefatos Comprobatórios Incluídos:**

| Arquivo | Descrição | Status |
|---------|-----------|--------|
| `audit_log.json` | Metadata da sessão · todos os hashes · assinatura RSA · validação Gemini | ✓ VERIFIED |
| `bundle.tar` | Pacote principal (SHA-256: `cef5a984c35d...`) | ✓ VERIFIED |
| `signature.bin` | RSA-2048 · PKCS#1v15 · SHA-256 · 256 bytes | ✓ VALID |
| `public.pem` | RSA 2048-bit public key | 🔓 PUBLIC |
| `input.txt` | Hash de input verificável | ✓ MATCH |
| `output.txt` | Hash de output verificável | ✓ MATCH |
| `brier_dataset_n142.csv` | Dataset de calibração (N=142, Seed=42) | ✓ VERIFIED |
| `validation.txt` | Output bruto da validação Gemini · AUDIT-SEAL | ✓ APPROVED |
| `SHA256` | Manifesto completo de hashes | 📋 MANIFEST |

---

## 📊 Protocolo 3.2 · Stress Test

### **Parâmetros de Execução:**
- **Temperature:** 0 (determinístico)
- **Seed:** 42 (reprodutibilidade total)
- **Iterações:** 12 ciclos documentados
- **Domínios:** 4 domínios críticos
  - Macroeconomia
  - Física de fronteira
  - Agronegócio
  - Transição energética & geopolítica
- **Questões Auditadas:** 18 questões
- **Cross-Model:** Gemini, Claude, GPT, DeepSeek
- **Cross-Sessão:** Com e sem histórico

---

## 🌍 Alinhamento Regulatório Mapeado

| Framework | Artigo/Requisito | Resposta ARIA OMEGA |
|-----------|------------------|---------------------|
| **EU AI Act** | Arts. 9, 13, 14 | Transparência ante-hoc · rastreabilidade completa por inferência individual |
| **BACEN 4.557** | Rastreabilidade | Cadeia de auditoria imutável SHA-256+RSA-2048 gerada por output |
| **LGPD** | Art. 20 | Explicação de decisões automatizadas com cadeia causal documentada |
| **NIST AI RMF 1.0** | GOVERN · MAP | 6 regras de governança induzidas empiricamente (6.1–6.6) + framework Glass Box de 42 requisitos |
| **ISO/IEC 42001:2023** | Transparência | Calibração via Brier Score + reprodutibilidade de protocolo |

---

## 📥 Download do Technical Evidence Brief

**Documento Principal:**
- 📄 [ARIA OMEGA — Technical Evidence Brief.pdf](./ARIA%20OMEGA%20%E2%80%94%20Technical%20Evidence%20Brief.pdf)
- **Versão:** GB-AUDIT-PROOF-v1.1
- **Data:** Julho 2026
- **Protocolo:** ADCW-O v1.0

---

## 🔍 Como Verificar Independentemente

### **Passo 1: Verificar integridade do PDF**
```bash
sha256sum "ARIA OMEGA — Technical Evidence Brief.pdf"
# Compare com o hash no arquivo SHA256
```

### **Passo 2: Extrair e verificar artefatos**
```bash
# O documento contém referências a:
# - audit_log.json
# - bundle.tar
# - signature.bin
# - public.pem
# - brier_dataset_n142.csv

# Verifique cada arquivo conforme instruções no §05 do documento
```

### **Passo 3: Reprodutibilidade**
```bash
# Execute com os mesmos parâmetros:
# Temperature = 0
# Seed = 42
# Protocol 3.2
# N = 142

# Compare seus resultados com os dados no brier_dataset_n142.csv
```

---

## 📄 Propriedade Intelectual

**Patente Depositada:**
- **INPI:** BR 10 2025 023744 0
- **Protocolo:** 870250099654
- **Data de Depósito:** 30/10/2025
- **Status:** Em exame
- **Título:** Arquitetura de governança e auditabilidade de raciocínio para modelos de linguagem de grande escala

---

## 👨‍💻 Autor

**Ale Balbim**  
AI Systems Architect  
Founder — Projeto INSÍGNIA  
📍 Ilhabela, SP, Brasil  
🔗 [LinkedIn](https://linkedin.com/in/alebalbim)  
📧 alebalbim@gmail.com

---

## 📝 Citação

Se você usar este trabalho em sua pesquisa, por favor cite:

```bibtex
@misc{balbim2026ariaomega,
  author = {Balbim, Carlos Alexandre dos Santos},
  title = {ARIA OMEGA: Glass Box Auditability Technical Evidence Brief},
  year = {2026},
  version = {GB-AUDIT-PROOF-v1.1},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/alebalbim/aria-omega-audit-verification}},
  note = {Patent Pending: INPI BR 10 2025 023744 0}
}
```

---

## ⚖️ Licença

Este repositório contém material técnico para fins de verificação independente e auditoria regulatória.

**Uso Permitido:**
- ✅ Verificação criptográfica independente
- ✅ Auditoria regulatória
- ✅ Pesquisa acadêmica
- ✅ Due diligence técnica

**Restrições:**
- ❌ Uso comercial sem autorização prévia
- ❌ Modificação ou derivação sem consentimento
- ❌ Remoção de atribuição ou AUDIT-SEAL

© 2026 Carlos Alexandre dos Santos Balbim · Projeto INSÍGNIA · Todos os direitos reservados

---

## 📞 Contato para Parcerias

Interessado em:
- Implementação do protocolo ARIA OMEGA em sua organização?
- Parcerias para testes piloto em ambientes regulados?
- Conversas sobre investimento ou pesquisa?

**Entre em contato:**
- 📧 alebalbim@gmail.com
- 🔗 [LinkedIn](https://linkedin.com/in/alebalbim)
- 📱 +55 12 98707-8703

---

<div align="center">

**AUDIT-SEAL:** `a7f3d9c2e1b4...`  
**Version:** GB-AUDIT-PROOF-v1.1 · **Protocol:** ADCW-O v1.0 · **Date:** July 2026

*"A integridade do corpus é demonstrada pela capacidade de detecção e correção documentada de falhas — seja por auditoria interna ou por revisão de terceiro."*

</div>