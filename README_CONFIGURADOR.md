# ITA Rocket Configurator

Sistema front-end completo para configuração de foguetes com interface intuitiva, biblioteca de componentes pré-cadastrados e exportação para JSON.

## 🚀 Características

### Biblioteca de Componentes
- **5 Foguetes Pré-cadastrados**: Modelos ITA Rocket de 2020 a 2024, cada um com configuração completa
- **Componentes Modulares**: Ogivas, fuselagens, aletas, motores e sistemas de recuperação
- **Fácil Seleção**: Clique para carregar presets ou adicionar componentes individuais

### Editor de Configuração
- **Visualizador SVG**: Representação visual do foguete em tempo real
- **Edição de Propriedades**: Modifique massa, dimensões, materiais e cores de cada componente
- **Gerenciamento de Componentes**: Adicione, remova e reorganize elementos
- **Resumo Automático**: Cálculo de massa total, empuxo e altitude estimada

### Mapa Integrado
- **Localização Padrão**: ITA - São José dos Campos, SP
- **Visualização Cartográfica**: Integração com Google Maps para futuras simulações

### Exportação e Importação
- **Exportar JSON**: Gere arquivo de configuração para uso em simuladores
- **Importar JSON**: Carregue configurações salvas anteriormente
- **Salvar Localmente**: Armazene configurações no navegador usando localStorage

## 🎨 Design

### Tema Neon Minimalista
- **Cores Primárias**: Ciano (#00d9ff) e Magenta (#ff006e)
- **Fundo**: Cinza muito escuro (#0f0f0f)
- **Superfícies**: Cinza escuro (#1a1a1a) com bordas neon
- **Feedback Visual**: Transições suaves e efeitos de brilho

### Layout
```
┌─────────────────────────────────────────────────────────────────┐
│ ITA ROCKET | Nome do Foguete | [Importar] [Salvar] [Exportar]  │
├──────────────┬──────────────────────────────┬──────────────────┤
│              │                              │                  │
│  BIBLIOTECA  │    VISUALIZADOR + MAPA      │  PROPRIEDADES    │
│              │                              │                  │
│  - Presets   │    ┌──────────────────────┐  │  Nome            │
│  - Componentes│   │   Foguete SVG        │  │  Material        │
│              │    │                      │  │  Cor             │
│              │    ├──────────────────────┤  │  Massa           │
│              │    │   Mapa Localização   │  │  Diâmetro        │
│              │    └──────────────────────┘  │  ...             │
│              │                              │                  │
│              │    Clique em componentes    │  [Remover]       │
│              │    para editar              │                  │
│              │                              ├──────────────────┤
│              │                              │  COMPONENTES     │
│              │                              │  - Lista         │
│              │                              │  - Totais        │
│              │                              │  - Resumo        │
│              │                              └──────────────────┘
└──────────────┴──────────────────────────────┴──────────────────┘
```

## 📋 Estrutura de Dados

### Foguete (Rocket)
```json
{
  "id": "ita-rocket-2024",
  "name": "ITA Rocket 2024",
  "description": "Foguete de última geração",
  "year": 2024,
  "components": [...]
}
```

### Componente (Component)
```json
{
  "id": "nose-cone-2024",
  "type": "nose-cone",
  "name": "Ogiva Ultra-Aerodinâmica 2024",
  "mass": 0.52,
  "diameter": 0.10,
  "length": 0.35,
  "material": "Fibra de Carbono 12K",
  "color": "#f0f0f0"
}
```

### Tipos de Componentes
- **nose-cone**: Ogiva (ponta do foguete)
- **fuselage**: Fuselagem (corpo principal)
- **fins**: Aletas (estabilização)
- **motor**: Motor (propulsão)
- **recovery**: Sistema de recuperação (paraquedas)

### Configuração Exportada
```json
{
  "id": "rocket-1234567890",
  "name": "Meu Foguete Customizado",
  "createdAt": "2026-04-24T21:00:00.000Z",
  "components": [...],
  "totalMass": 5.25,
  "totalThrust": 2500,
  "estimatedAltitude": 476
}
```

## 🎯 Como Usar

### Carregar um Preset
1. Abra a aba **Presets** na barra lateral esquerda
2. Clique em um dos 5 foguetes ITA Rocket (2020-2024)
3. A configuração será carregada automaticamente

### Criar Configuração Customizada
1. Abra a aba **Componentes** na barra lateral esquerda
2. Selecione o tipo de componente (Ogivas, Fuselagens, etc.)
3. Clique no **+** para adicionar à configuração
4. Clique no componente no painel direito para editar propriedades
5. Modifique nome, material, cor, massa, dimensões, etc.

### Editar Propriedades
1. Clique em um componente na **lista de componentes** (painel direito)
2. O painel **Propriedades** será preenchido com os dados
3. Edite os campos desejados
4. As mudanças são aplicadas em tempo real

### Visualizar Foguete
- O **visualizador central** mostra representação SVG do foguete
- Clique em partes do foguete para selecioná-las
- O **mapa** abaixo mostra localização de lançamento padrão (ITA)

### Exportar Configuração
1. Clique em **Exportar JSON** na barra superior
2. Um arquivo `.json` será baixado com a configuração completa
3. Este arquivo pode ser usado em simuladores ou importado depois

### Importar Configuração
1. Clique em **Importar** na barra superior
2. Selecione um arquivo `.json` previamente exportado
3. A configuração será carregada automaticamente

### Salvar Localmente
1. Clique em **Salvar** na barra superior
2. A configuração é armazenada no localStorage do navegador
3. Você pode recarregar a página sem perder os dados

## 📊 Resumo da Configuração

O painel inferior direito mostra:
- **Nome**: Nome do foguete
- **Componentes**: Quantidade total
- **Massa Total**: Soma de todas as massas (kg)
- **Empuxo Total**: Soma de todos os empuxos (N)
- **Altitude Estimada**: Cálculo simplificado baseado em empuxo/massa (m)
- **Breakdown**: Contagem de cada tipo de componente
- **Aviso**: Alerta se faltam componentes essenciais

## 🔧 Componentes Disponíveis

### Ogivas (Nose Cones)
- Cônica Básica (0.40 kg)
- Parabólica (0.42 kg)
- Power Series (0.45 kg)

### Fuselagens
- Padrão em Alumínio 6061 (1.8 kg)
- Leve em Fibra de Carbono (1.5 kg)
- Reforçada em Alumínio 7075-T6 (2.3 kg)

### Aletas
- Trapezoidais (0.30 kg, 3 unidades)
- Delta (0.35 kg, 4 unidades)
- Canard (0.38 kg, 4 unidades)

### Motores
- L500 Sólido (1.2 kg, 500 N)
- L1000 Sólido (1.8 kg, 1000 N)
- H1500 Híbrido (2.1 kg, 1500 N)

### Sistemas de Recuperação
- Paraquedas Básico (0.20 kg, 1.0 m)
- Paraquedas Duplo (0.28 kg, 1.4 m)
- Sistema Avançado (0.35 kg, 1.8 m)

## 🎨 Personalização

### Cores
- Clique no ícone de cor no painel de propriedades
- Selecione uma cor ou insira código hexadecimal
- A cor será refletida no visualizador

### Materiais
- Edite o campo "Material" para documentar o tipo
- Exemplos: Fibra de Carbono, Alumínio 7075, Kevlar, etc.

### Dimensões
- Modifique massa, diâmetro, comprimento conforme necessário
- Valores são refletidos nos cálculos de resumo

## 📱 Responsividade

O sistema foi desenvolvido com layout flexível que se adapta a diferentes tamanhos de tela. Para melhor experiência, recomenda-se:
- **Desktop**: 1920x1080 ou superior
- **Tablet**: 1024x768 ou superior
- **Mobile**: Funciona, mas layout otimizado para telas maiores

## 🔮 Funcionalidades Futuras

- Integração com engine de simulação de foguetes
- Testes operacionais simulados de desempenho
- Visualização 3D avançada
- Cálculos aerodinâmicos detalhados
- Histórico de versões
- Compartilhamento de configurações
- Análise de estabilidade

## 📝 Notas Técnicas

### Arquitetura
- **Frontend**: React 19 + TypeScript
- **Styling**: Tailwind CSS 4 + CSS customizado
- **Estado**: React Hooks (useRocketConfig)
- **Dados**: JSON estático em `public/data.json`
- **Persistência**: localStorage para salvar localmente

### Arquivos Principais
- `client/src/pages/Home.tsx`: Página principal
- `client/src/hooks/useRocketConfig.ts`: Gerenciamento de estado
- `client/src/components/`: Componentes React
- `client/public/data.json`: Base de dados de foguetes e componentes
- `client/src/types/index.ts`: Definições de tipos TypeScript

### Cálculos
- **Massa Total**: Soma simples de todas as massas
- **Empuxo Total**: Soma de todos os empuxos
- **Altitude Estimada**: `(totalThrust / totalMass) * 100` metros (fórmula simplificada)

## 🐛 Troubleshooting

### Componentes não aparecem no visualizador
- Verifique se o componente foi adicionado (deve aparecer na lista direita)
- Certifique-se de que o tipo de componente está correto

### Dados não salvam
- Verifique se localStorage está habilitado no navegador
- Tente exportar para JSON como backup

### Mapa não carrega
- Verifique conexão com internet
- Google Maps pode estar bloqueado em sua região

## 📞 Suporte

Para dúvidas ou sugestões sobre o configurador, entre em contato com a equipe ITA Rocket.

---

**Versão**: 1.0.0  
**Última atualização**: Abril de 2026  
**Desenvolvido para**: ITA Rocket Team
