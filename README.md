# Holiday AI Summarization - Power Platform Solution

## 🎥 Vídeo de Demonstração

🎬 **[Assistir Demonstração Completa](Romaos_HolidayAISummarization_Demo.mp4)**

*Clique no link acima para assistir à demonstração completa da solução Holiday AI Summarization em funcionamento*

**Duração:** ~3 minutos | **Formato:** MP4

## 📋 Visão Geral

Esta solução Power Platform automatiza o processo de sumarização de emails durante períodos específicos, utilizando inteligência artificial para gerar resumos inteligentes do conteúdo dos emails.

## 🎯 Funcionalidades

### 🤖 Automação de Sumarização de Emails (Power Automate)
- **Busca Inteligente**: Recupera emails do Outlook em um intervalo de datas específico
- **Processamento de Conteúdo**: Converte conteúdo HTML dos emails para texto puro
- **IA Integrada**: Utiliza AI Builder para gerar resumos contextuais e relevantes
- **Paginação Automática**: Processa grandes volumes de emails com paginação do Microsoft Graph API

### 📱 Interface do Usuário (Power Apps)
- Aplicação Canvas intuitiva para interação com o usuário
- Interface simples para definir período de análise
- Exibição clara dos resultados de sumarização

## 🏗️ Arquitetura da Solução

### Componentes Principais

1. **Power Automate Flow**: `Romaos_HolidayAIAutomation`
   - Trigger manual via Power App
   - Integração com Microsoft Graph API
   - Processamento de dados com AI Builder
   - Retorno de resposta estruturada

2. **Power Apps Canvas App**: `rms_holidayemailsummarization_ea69b`
   - Interface amigável para definição de parâmetros
   - Conexão direta com o fluxo de automação
   - Exibição de resultados

3. **Conexões Utilizadas**:
   - Microsoft Dataverse
   - Microsoft Graph (via HTTP)
   - AI Builder
   - Conversão de Serviços

### Fluxo de Dados

```
Power App → Power Automate → Microsoft Graph API → AI Builder → Resposta
     ↓              ↓              ↓              ↓              ↓
  Interface     Processamento    Busca Emails   Sumarização    Resultado
```

## 📦 Estrutura do Projeto

```
holidayAISummarization_powerplatform/
├── HolidaySeasonRecap_1_0_0_0/          # Solução descompactada
│   ├── solution.xml                      # Manifesto da solução
│   ├── customizations.xml               # Personalizações
│   ├── CanvasApps/                      # Aplicações Power Apps
│   │   ├── rms_holidayemailsummarization_ea69b_DocumentUri.msapp
│   │   ├── rms_holidayemailsummarization_ea69b_BackgroundImageUri
│   │   └── rms_holidayemailsummarization_ea69b_AdditionalUris0_identity.json
│   └── Workflows/                       # Fluxos Power Automate
│       └── Romaos_HolidayAIAutomation-F2564C5D-46E7-F011-8544-000D3A37715A.json
└── HolidaySeasonRecap_1_0_0_0.zip       # Arquivo da solução para importação
```

## 🔧 Pré-requisitos

### Licenças Necessárias
- Power Apps Premium ou superior
- Power Automate Premium
- AI Builder créditos
- Microsoft 365 (para acesso ao Outlook)

### Conexões e Permissões
- Acesso ao Microsoft Graph API
- Permissões de leitura para emails do Outlook
- Conexão com Dataverse
- Acesso ao AI Builder

## 🚀 Instalação e Configuração

### 1. Importação da Solução
```bash
# O arquivo pronto para importação está disponível em:
HolidaySeasonRecap_1_0_0_0.zip
```

### 2. Configuração das Conexões
1. **Microsoft Graph API**: Configure autenticação OAuth
2. **AI Builder**: Verifique créditos disponíveis
3. **Dataverse**: Configure ambiente de destino

### 3. Personalização (Opcional)
- Ajuste os parâmetros de busca de emails
- Personalize o prompt de IA conforme necessário
- Modifique a interface da aplicação Canvas

## 📊 Como Usar

1. **Abra a Power App** no seu dispositivo ou navegador
2. **Defina o período** de análise (datas início e fim)
3. **Execute a automação** clicando em "Executar"
4. **Aguarde o processamento** dos emails
5. **Visualize o resumo** gerado pela IA

## 🔍 Detalhes Técnicos

### API Endpoints Utilizados
- `GET /me/messages` - Busca de emails com filtros de data
- `POST /aibuilderpredict_customprompt` - Sumarização via AI Builder
- `POST /conversionservice/HtmlToText` - Conversão de HTML para texto

### Estrutura de Dados
```json
{
  "text": "2024-12-01",     // Data início
  "text_1": "2024-12-31",  // Data fim
  "response": "Resumo gerado pela IA..."
}
```

### Limitações e Considerações
- Máximo de 60 iterações para paginação (configurável)
- Timeout de 1 hora por execução
- Limite de processamento do AI Builder
- Requer conectividade com Microsoft 365

## 🏢 Informações do Publisher

- **Nome**: Romão's
- **Email**: contato@romaos.com.br
- **Website**: www.romaos.com.br
- **Prefixo**: rms

## 📬 Contato

**Douglas Romão**
- **LinkedIn**: [https://www.linkedin.com/in/douglas-romao/](https://www.linkedin.com/in/douglas-romao/)
- **Email**: contato@romaos.com.br

## 📝 Notas de Versão

### Versão 1.0.0.0
- ✅ Implementação inicial da automação
- ✅ Interface básica do usuário
- ✅ Integração com AI Builder
- ✅ Suporte a paginação de emails
- ✅ Conversão HTML para texto
