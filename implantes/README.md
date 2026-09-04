# LP — Dra. Paula Cardoso | Implantes Dentários e Prótese Protocolo

Landing page estática de captação para implantes dentários e prótese protocolo.
Cliente: Dra. Paula Cardoso (CRO-GO 7676) — Goiânia/GO.

- LP de implantes: `implantes/index.html` (um ou mais dentes)
- LP de prótese protocolo: `implante-protocolo/index.html` (arcada completa)
- Imagens: `images/`
- Fontes: arquivos locais (Sora + Instrument Serif), sem bloqueio por terceiros
- Material bruto do cliente: `_material-cliente/` (**não subir para o servidor**)

Desenvolvido por **3ADS**.

- **Implantes:** <https://paulacardosoessence.com.br/implantes/>
- **Prótese protocolo:** <https://paulacardosoessence.com.br/implante-protocolo/>
- **Repositório de produção:** <https://github.com/atendimento3ads/paula-cardoso-essence>

> ⚠️ O GitHub Pages é **público**. Qualquer pessoa com o link vê a página e as
> fotos dos pacientes. Enquanto a autorização de uso de imagem não estiver
> confirmada (item 4 abaixo), tratar esse link como interno — não divulgar.

---

## Estrutura da página

| Seção | Conteúdo | CTA |
|---|---|---|
| Hero | H1 + 4 selos + foto | Falar pelo WhatsApp |
| 02 · Entenda o seu caso | 3 cards adaptados ao tema de cada LP | Quero entender meu caso |
| 03 · Antes de indicar | 5 critérios de avaliação + foto | Agendar minha avaliação |
| 04 · Na prática | Casos clínicos em três etapas | Falar com a equipe |
| 05 · Passo a passo | Linha do tempo de 4 etapas | Quero começar pela avaliação |
| 06 · Uma dúvida comum | Carga imediata: 4 fatores + infográfico | Quero saber o que é possível no meu caso |
| 07 · Acompanhamento | 3 pilares + bloco da Dra. Paula | Falar com a equipe pelo WhatsApp |
| 08 · Para esclarecer | FAQ com 6 perguntas (accordion) | Falar pelo WhatsApp |
| 09 · Para começar | CTA final + 3 selos | Agendar minha avaliação |
| Rodapé | Responsável técnico, CRO, CNPJ | — |

Botão flutuante de WhatsApp ativo durante toda a navegação, com mensagem
automática específica para implantes ou prótese protocolo.

As duas copys foram aplicadas em páginas independentes, preservando a identidade
visual aprovada. A LP principal comunica implantes para um ou mais dentes; a LP
de protocolo comunica a reabilitação fixa de arcada completa.

---

## Dados e pendências

### 1. Número do WhatsApp
A copy revisada trouxe **62 99889-0605**. As duas páginas usam:

```
https://wa.me/5562998890605
```

Cada LP usa sua própria mensagem automática para identificar o interesse em
implantes ou prótese protocolo.

### 2. CNPJ
O rodapé e os dados estruturados usam `59.241.454/0001-05`.

### 3. Autorização de uso de imagem — IMPORTANTE
As fotos em `images/casos/` vieram da pasta enviada pela cliente. **A copy pede
"casos autorizados"** — confirmar com a Dra. Paula quais pacientes têm
autorização de uso de imagem assinada. Como a página já está num Pages público,
essa checagem vale para agora, não só para o lançamento. Fotos sem autorização
devem sair da seção e do repositório.

A seção 04 apresenta três estudos de caso completos, cada um com registros de
antes, durante e depois: Ricardo, Maria e Val. Os originais e demais registros
clínicos continuam em `_material-cliente/casos-nao-usados/`, fora do deploy e
fora do Git.

### 4. Casos clínicos
Cada paciente deve aparecer sempre com uma sequência coerente — condição
inicial, etapa clínica e resultado final. Nunca publicar uma imagem de "antes"
isolada ou misturar fotos de pacientes diferentes no mesmo card.

---

## Identidade visual

Base: Figma *[LP Base] Paula Cardoso - AGO26*.
Todas as cores estão em variáveis CSS no topo do `index.html` — mexer lá muda a
página inteira.

| Variável | Valor | Uso |
|---|---|---|
| `--wine` | `#7A1A3D` | Cor primária: botões, destaques |
| `--wine-deep` | `#5C1029` | Hover e fundo da seção de etapas |
| `--wine-soft` | `#A8456A` | Apoio |
| `--wine-tint` | `#F3E4EA` | Fundos suaves, ícones |
| `--cream` | `#F4EFEB` | Fundo quente principal |
| `--cream-2` | `#EAE1D9` | Faixa alternada |
| `--ink` | `#1E1613` | Texto principal |

**Tipografia**
- Títulos e corpo: **Sora** — títulos com tracking de −5%
- Palavras em destaque: **Instrument Serif itálico**

A Apple Garamond foi testada como fonte de destaque, mas é licenciada da Apple e
não pode ser carregada via Google Fonts — substituída pela Instrument Serif a
pedido do cliente. Detalhes em `fonts/LEIA-ME.txt`.

---

## Técnico

- Responsivo: 3 breakpoints (1040px, 900px, 760px, 520px). A linha do tempo vira
  vertical abaixo de 900px.
- Acessibilidade: respeita `prefers-reduced-motion`, botões do carrossel com
  `aria-label`, FAQ em `<details>` nativo (funciona sem JS).
- SEO: meta description, Open Graph e JSON-LD com schema `Dentist` + `FAQPage`
  (as 6 perguntas do FAQ estão marcadas para rich results do Google).
- Sem dependências externas além do Google Fonts.

### Publicação
O arquivo `.cpanel.yml` do repositório principal copia as duas LPs e os ativos compartilhados para o domínio de produção. Após cada push na branch `main`, atualizar o repositório no cPanel e executar o deploy do commit mais recente.

### Rodar localmente
Qualquer servidor estático serve. Exemplo:

```bash
cd "paula-cardoso-essence" && python3 -m http.server 8080
```
