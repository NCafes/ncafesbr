# Como editar o site da N Cafés

Todo o conteúdo dos produtos fica em cinco arquivos, na pasta `conteudo/`:

- `cafes.json` — os cafés por região (N11, N28, N34, N35, N77)
- `microlotes.json` — os microlotes especiais
- `outros.json` — drip coffee, boné, cerveja e outros produtos
- `social.json` — os projetos do Café Social
- `produtores.json` — as fotos e legendas dos produtores parceiros

As fotos ficam na pasta `img/`.

## Jeito recomendado: painel de edição (sem mexer em código)

Configuração única (uns 20 minutos):

1. Crie uma conta grátis no GitHub (github.com) e um repositório chamado `ncafes-site`.
2. Envie para o repositório todos os arquivos desta pasta (botão "Add file" → "Upload files").
3. Crie o arquivo de configuração do painel. Ele precisa se chamar `.pages.yml` (com ponto no início).
   Arquivos que começam com ponto ficam ocultos no Mac e costumam não subir. Por isso:
   - No GitHub, abra o arquivo `pages.yml` (sem ponto) que você acabou de enviar.
   - Clique no lápis (Edit). No campo do nome, no topo, acrescente um ponto antes: `.pages.yml`.
   - Clique em "Commit changes". Pronto: o arquivo foi renomeado.
4. No Cloudflare: Workers & Pages → Create application → Pages → "Connect to Git" → escolha `ncafes-site`.
   - Framework preset: None
   - Build command: deixe vazio
   - Build output directory: `/`
5. Entre em app.pagescms.org, faça login com o GitHub, instale o app no repositório `ncafes-site` e abra o repositório.

No dia a dia:

1. Abra app.pagescms.org.
2. Escolha "Cafés por região", "Microlotes especiais", "Drip, boné e outros produtos", "Café Social" ou "Fotos dos produtores".
3. Edite textos, troque ou adicione fotos e clique em "Save".
4. Em cerca de 1 minuto o Cloudflare publica o site atualizado.

Dicas:

- Para tirar um produto do ar sem apagar, desmarque "Disponível".
- Para um microlote novo, clique em "Add an entry" dentro de "Microlotes especiais".
- Campos vazios (preço, notas sensoriais, selo, legenda) simplesmente não aparecem no site.
- Para mudar a ordem das fotos dos produtores, arraste os itens na lista do painel.
- A primeira foto é a do card. As outras aparecem na página do produto.
- Se não houver nenhum microlote disponível, o site mostra um aviso convidando a seguir o Instagram.

## Jeito manual (sem GitHub)

1. Abra o arquivo `.json` desejado num editor de texto e altere os textos entre aspas.
2. Coloque fotos novas na pasta `img/` e escreva o caminho, por exemplo `"/img/microlote-julho.jpg"`.
3. No Cloudflare, abra o projeto e envie a pasta inteira de novo ("Create new deployment").

Atenção: mantenha as aspas, vírgulas e colchetes do arquivo. Um erro de digitação faz a lista não aparecer.
