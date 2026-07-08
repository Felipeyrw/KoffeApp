<div align="center">

# ☕ Koffe

### Gestão inteligente para barbearias e clínicas de massoterapia

[![Flutter](https://img.shields.io/badge/Flutter-3.4+-02569B?logo=flutter&logoColor=white)](https://flutter.dev)
[![Dart](https://img.shields.io/badge/Dart-3.x-0175C2?logo=dart&logoColor=white)](https://dart.dev)
[![Supabase](https://img.shields.io/badge/Supabase-Backend-3FCF8E?logo=supabase&logoColor=white)](https://supabase.com)
[![License](https://img.shields.io/badge/License-Proprietary-red)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Android-brightgreen?logo=android)](https://flutter.dev)

[![漳 Status](https://img.shields.io/badge/Status-Em%20desenvolvimento-yellow)]()
[![漳 Version](https://img.shields.io/badge/Version-0.1.0-blue)]()

---

**Koffe** é um aplicativo mobile que transforma a gestão de barbearias e clínicas de massoterapia em uma experiência simples, segura e poderosa — funciona 100% offline e sincroniza na nuvem quando conectado.

[Fale comigo sobre parcerias](mailto:contato@koffe.app) · [Reportar bug](https://github.com/Felipeyrw/koffe/issues) · [Contribuir](#-quero-contribuir)

</div>

---

## 🔥 Por que Koffe?

A maioria dos sistemas de gestão para barbearias são **caros, complexos e dependentes de internet**. Koffe foi criado para resolver isso:

> **Um app que funciona na rua, no metrô, no sertão — e sincroniza quando volta a internet.**

### Os 3 pilares do Koffe

| Pilar | O que isso significa |
|-------|---------------------|
| 🏔️ **Offline-First** | Dados salvos localmente primeiro. Funciona 100% sem internet. Sincroniza automaticamente. |
| 🤖 **Agendamento por Voz** | Fale em português, a IA preenche o formulário. Agende em 10 segundos. |
| 🔐 **Segurança de Verdade** | Banco criptografado (SQLCipher), autenticação biométrica, rastreamento de dispositivos. |

---

## ✨ Funcionalidades

### 🗓️ Agenda Inteligente
- Calendário visual com 3 modos: **Dia / Semana / Mês**
- Slots de tempo gerados automaticamente a partir dos turnos configurados
- Bloqueio automático de **férias**, **folgas** e **dias sem expediente**
- Intervalo configurável entre atendimentos
- Agendamento por **voz com IA** (Groq) — fale em português, o sistema entende

### 👥 CRM de Clientes
- Cadastro completo com telefone, WhatsApp, e-mail e observações
- **Toque único para WhatsApp** — cliente fala com o barbeiro na hora
- Histórico de atendimentos por cliente
- Busca em tempo real e exclusão com **undo** (desfazer)

### 💰 Controle Financeiro Completo
- **Saldo do período** com comparação percentual (ex: "+12,5% vs. ontem")
- Despesas **fixas e variáveis** com controle de vencimento
- Pagamentos **a pagar e a receber** com status visual
- Alerta de despesas atrasadas
- **Lucro líquido** calculado automaticamente

### 📊 Dashboard & Relatórios
- Gráficos de evolução com **agrupamento adaptativo** (diário, mensal, semestral)
- Melhor e pior dia do período
- **Ranking de serviços** por faturamento
- Dedução de **impostos** configurável (ISS, PIS, COFINS)
- Exportação em **PDF e Excel**

### 🔔 Notificações Contextuais
- 6 tipos de notificações configuráveis:
  - Lembrete de agendamento (10min, 30min, 1h, 2h, 1 dia antes)
  - Resumo do dia
  - Agenda de amanhã
  - Alerta de despesas
- Mensagens geradas dinamicamente em **estilo brasileiro**

### ⚙️ Configurações Avançadas
- **Serviços**: catálogo com nome, preço (R$) e duração
- **Horários**: turnos por dia da semana, folgas pontuais, férias
- **Formas de pagamento**: Pix, cartão, dinheiro — com ativação/desativação
- **Impostos**: categorias com alíquotas diferentes
- **Temas**: personalização visual com preview

### 🔒 Segurança
- **SQLCipher** — banco local criptografado
- **Autenticação biométrica** — impressão digital / Face ID
- **Armazenamento seguro** — tokens em Keychain/Keystore
- **Rastreamento de dispositivos** — detecção de logins suspeitos
- **Exclusão protegida** — operações sensíveis exigem biometria

### 📡 Sincronização Inteligente
- **14 sync managers** especializados
- Retry automático com backoff exponencial
- Verificação de conectividade antes de sincronizar
- Mutex para evitar sincronizações concorrentes
- Merge automático entre dispositivos

---

## 🎯 Para quem é?

| Perfil | Como Koffe ajuda |
|--------|-----------------|
| **Barbeiro autônomo** | Organiza agenda, controla financeiro, não perde cliente por esquecimento |
| **Barbearia com equipe** | Gerencia múltiplos profissionais, comissões e horários |
| **Massoterapeuta** | Dashboard focado em sessões, tempo trabalhado e comunicação com cliente |
| **Dono que quer escalar** | Relatórios, impostos, exportação — dados para decisões |

---

## 🛠️ Tech Stack

```
Frontend        → Flutter 3.4+ (Dart)
Estado          → Provider + GetX
Banco Local     → SQLite + SQLCipher (criptografado)
Backend         → Supabase (PostgreSQL + Auth + Storage)
Edge Functions  → Deno (Supabase Edge)
IA              → Groq (agendamento por voz)
Gráficos        → fl_chart
Exportação      → PDF + Excel + Compartilhamento
Notificações    → flutter_local_notifications + Timezone
Segurança       → local_auth + flutter_secure_storage + device_info_plus
```

---

## 📱 Capturas de Tela

<div align="center">

> *Em breve — previews do app em funcionamento*

</div>

---

## 🗺️ Roadmap

### ✅ Implementado
- [x] Agenda visual com 3 modos (Dia/Semana/Mês)
- [x] Agendamento por voz com IA (Groq)
- [x] CRM completo com WhatsApp integrado
- [x] Controle financeiro (a pagar/receber, despesas fixas/variáveis)
- [x] Dashboard com gráficos adaptativos
- [x] Exportação PDF e Excel
- [x] Sistema de notificações contextuais
- [x] Autenticação biométrica
- [x] Sincronização offline-first (14 managers)
- [x] Banco criptografado (SQLCipher)
- [x] Multi-negócio (barbearia + massoterapia)
- [x] Gestão de profissionais e comissões

### 🚧 Em desenvolvimento
- [ ] Publicação na Google Play Store
- [ ] Widgets Android (tela inicial)
- [ ] Backup automático configurável
- [ ] Dashboard web companion

### 🔮 Futuro
- [ ] Suporte iOS (App Store)
- [ ] Suporte Web (PWA)
- [ ] Integração WhatsApp Business API
- [ ] IA para análise financeira preditiva
- [ ] Módulo de fidelidade / pontos
- [ ] API pública para integrações

---

## 🤝 Parcerias & Contribuições

### Quero contribuir

Este é um **projeto privado em fase ativa de desenvolvimento**. O código-fonte não está disponível publicamente, mas existem formas de participar:

- **Flutter / Dart** — Ajude com features, testes ou otimizações
- **UI/UX Design** — Melhore a experiência do usuário
- **Backend / Supabase** — Edge Functions, banco de dados, APIs
- **Business Development** — Ajude a levar Koffe para barbearias
- **Marketing / Conteúdo** — Crie conteúdo sobre gestão de barbearias

### Quero uma parceria estratégica

Se você é:
- 🏢 **Distribuidor** de produtos para barbearias
- 📚 **Criador de cursos** de barbearia / massoterapia
- 💼 **Contador** especializado em MEI / beleza e estética
- 🤳 **Influenciador** do nicho de barbearias
- 🏗️ **Franquia** ou rede de barbearias

**[Fale comigo](mailto:contato@koffe.app)** — estou aberto a parcerias que beneficiem ambas as partes.

### Quer ser investidor?

Koffe está em fase inicial e busca:
- Investidores-anjo com experiência em SaaS / mobile
- Mentoria de negócio
- Conexões no mercado de barbearias

**[Entre em contato](mailto:contato@koffe.app)**

---

## 📊 Números do Projeto

| Métrica | Valor |
|---------|-------|
| Arquivos Dart | 174 |
| Linhas de código | 41.000+ |
| Módulos funcionais | 12 |
| Sync managers | 14 |
| Tipos de notificação | 6 |
| Temas visuais | 3 |
| Stack principal | Flutter + Supabase |

---

## 📞 Contato

| Canal | Link |
|-------|------|
| 📧 Email | [contato@koffe.app](mailto:contato@koffe.app) |
| 🐙 GitHub | [Felipeyrw/koffe](https://github.com/Felipeyrw/koffe) |
| 🐛 Issues | [GitHub Issues](https://github.com/Felipeyrw/koffe/issues) |

---

## 📄 Licença

Koffe é um software **privado e proprietário**. Todos os direitos reservados.

O uso, reprodução ou distribuição não autorizada é estritamente proibido.

Para informações de licenciamento, entre em contato: [contato@koffe.app](mailto:contato@koffe.app)

---

<div align="center">

**Feito com ☕ e muito café por [Felipe](https://github.com/Felipeyrw)**

*"A gestão da sua barbearia, na palma da sua mão."*

</div>
