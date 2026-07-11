# MOVIMENTO-lib

**MOVIMENTO-lib** é uma biblioteca aberta de conhecimento livre organizada em arquivos JSON. O objetivo do projeto é reunir conteúdos educacionais, cursos, mentorias, fontes e materiais de apoio em um formato simples, reutilizável e fácil de integrar em aplicativos, sites, plataformas de estudo, bots, ferramentas de IA e outros projetos digitais.

Qualquer pessoa pode participar, melhorar os conteúdos existentes ou adicionar novos conhecimentos para ampliar a biblioteca.

## Propósito

Este repositório nasceu para facilitar o acesso ao conhecimento livre. Em vez de manter o conteúdo preso a uma única aplicação, o MOVIMENTO-lib armazena as informações em arquivos JSON que podem ser baixados, lidos, reaproveitados e integrados por qualquer pessoa.

A ideia central é:

- democratizar o acesso a conteúdos educacionais;
- permitir que desenvolvedores integrem conhecimento em seus próprios aplicativos;
- criar uma base colaborativa, aberta e evolutiva;
- manter as fontes e os créditos visíveis para valorizar quem contribui;
- facilitar a criação de experiências de aprendizagem em múltiplos idiomas e formatos.

## Como o repositório está organizado

O conteúdo é separado por categorias e temas. Alguns exemplos de diretórios presentes no projeto:

```text
curso/
  python/
    python.json
    fonte.json
  javascript/
    javascript.json
    fonte.json
  html/
    html.json
    fonte.json

mentoria/
  exemplo/
    aula1.json

home/
  imagens usadas para representar conteúdos e categorias
```

Em geral, cada conteúdo possui:

- um arquivo principal `.json` com o conteúdo educacional;
- um arquivo `fonte.json` com informações de fonte, autoria, contribuidores ou créditos;
- opcionalmente, arquivos de mídia, como imagens ou áudios.

## Como usar os arquivos JSON

Você pode baixar qualquer arquivo JSON deste repositório e usá-lo em seu projeto. Por exemplo, um aplicativo pode carregar um curso com JavaScript usando `fetch`:

```js
async function carregarCurso() {
  const resposta = await fetch('curso/python/python.json');
  const curso = await resposta.json();

  console.log(curso.title.pt);
  console.log(curso.description.pt);
}

carregarCurso();
```

Também é possível consumir os arquivos em outras linguagens, como Python:

```python
import json

with open('curso/python/python.json', 'r', encoding='utf-8') as arquivo:
    curso = json.load(arquivo)

print(curso['title']['pt'])
print(curso['description']['pt'])
```

## Regra importante: exibição das fontes

Para usar esta biblioteca em qualquer aplicativo, site, sistema, ferramenta ou integração, é necessário mostrar as fontes e os créditos relacionados ao conteúdo utilizado.

Ao integrar um arquivo JSON da biblioteca, o aplicativo deve exibir de forma clara:

- a origem do conteúdo;
- os contribuidores, quando informados;
- links de referência ou perfis, quando existirem;
- o repositório MOVIMENTO-lib como fonte da biblioteca.

Os dados de fonte normalmente ficam em arquivos chamados `fonte.json`. Exemplo de estrutura:

```json
{
  "contributors": {
    "source": "MOVIMENTO BIBLIOTECA",
    "url": "https://github.com/versaodeluxe18/MOVIMENTO-lib",
    "items": [
      {
        "name": "Nome do contribuidor",
        "profile": "https://github.com/usuario",
        "avatar": "https://exemplo.com/avatar.png"
      }
    ]
  }
}
```

## Como contribuir

Contribuições são bem-vindas. Você pode participar adicionando novos conteúdos, corrigindo informações, melhorando traduções, incluindo fontes ou organizando arquivos existentes.

### Sugestão para adicionar um novo conteúdo

1. Escolha a categoria adequada, como `curso/` ou `mentoria/`.
2. Crie uma pasta com o nome do tema.
3. Adicione o arquivo principal do conteúdo em formato `.json`.
4. Adicione um arquivo `fonte.json` com as fontes e créditos.
5. Verifique se o JSON está válido.
6. Envie sua contribuição por pull request.

### Boas práticas para conteúdos

- Use linguagem clara e acessível.
- Sempre informe fontes e créditos.
- Evite conteúdo sem referência quando ele depender de dados técnicos, históricos ou verificáveis.
- Mantenha a estrutura dos arquivos consistente com os conteúdos já existentes.
- Quando possível, inclua suporte a múltiplos idiomas.
- Revise erros de digitação, links quebrados e JSON inválido antes de contribuir.

## Validação de JSON

Antes de enviar alterações, valide os arquivos JSON modificados. Um exemplo simples usando Python:

```bash
python -m json.tool curso/python/python.json > /dev/null
```

Para validar todos os arquivos JSON do repositório:

```bash
find . -name '*.json' -print0 | xargs -0 -n1 python -m json.tool > /dev/null
```

## Licença e uso

Este projeto foi criado para compartilhar conhecimento livre. Ao reutilizar os conteúdos, mantenha as fontes visíveis e preserve os créditos dos contribuidores.

Se você usar o MOVIMENTO-lib em um aplicativo, mencione este repositório como origem da biblioteca e exiba as fontes relacionadas aos conteúdos usados.

## Comunidade

O MOVIMENTO-lib cresce com a participação de pessoas que acreditam em conhecimento aberto. Se você tem algo para ensinar, corrigir ou melhorar, sua contribuição é bem-vinda.
