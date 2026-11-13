# Carta de vendas – Tosa Bebê Shih Tzu (Giovanna Rivaroli)

Página de vendas em formato de **carta de vendas escrita**, com a **VSL no topo** (YouTube, ID `Wvw02ExL6Ug`, versão sem o módulo 2), do curso Tosa Bebê Shih Tzu da groomer Giovanna Rivaroli (GR Groomers, Guarulhos).
Repositório irmão (VSL, no ar em https://groomergiorivaroli.com.br/): `viniciusgestortrafego-stack/giovannagroomer`.
Todo o conteúdo, código e mensagens ao usuário em **português do Brasil**.

## Produto desta página
Só o que foi feito no **Bruninho** (Shih Tzu macho): banho e preparação · secagem correta · técnica da tosa bebê · acabamento e finalização · rostinho redondo.
Curso de cerca de 2 horas. Preço: **R$ 127 à vista ou 12x de R$ 13,13**.

**Não falar** do outro modelo do curso completo (a fêmea Amora, estilo Chanel e penteado), nem de "2 modelos / 2 texturas / 2 variações de rosto".
Imagens/vídeos da Amora e de cães com penteado não entram aqui (ex.: `shihtzu-giro-360`, `maltes-bandana`, `shihtzu-branco-laco-azul`, `maltes-azul-tule-pata-cilindrica`, `shihtzu-laco-verde-amarelo`, `shihtzu-laco-preto-bandana-poa`, print `feedback-whatsapp-chanel-tosa-bebe`). Na dúvida, pergunte antes de usar uma foto.

## Estrutura
- `index.html`: a página inteira (HTML, CSS e JS inline, sem build e sem dependências).
- `web/`: imagens (`.jpg`) e, quando houver, vídeos curtos (`.mp4`) usados na página.

Não há `package.json`, framework nem testes. Para conferir, abra o `index.html` no navegador (Playwright já está instalado no ambiente cloud).

## Deploy
Site à parte, em subdomínio próprio na **Hostinger** (`tosabebê.groomergiorivaroli.com.br`; no DNS o "ê" vira punycode, e `tosabebe` sem acento é mais seguro, a confirmar), conectado a este repositório com implantação automática. Checkout na Hotmart; garantia de 7 dias.
**Pendente:** definir a branch que a Hostinger publica (provavelmente `main`) e registrar aqui. Mudanças: branch de trabalho → PR para `main` → merge. Se a Hostinger publicar outra branch, atualizá-la depois do merge sem reescrever histórico.

## Configuração (bloco `CONFIG` no `<script>` do fim da página)
- `checkoutUrl`: checkout da Hotmart (`https://pay.hotmart.com/B108393974V?checkoutMode=10`, o mesmo link do site irmão; o valor cobrado é definido na Hotmart e deve ser R$ 127 / 12x R$ 13,13). Usado só no botão da caixa de preço; os demais botões rolam até `#oferta`. Se vazio, o botão não leva a lugar nenhum.
- `whatsappUrl`: botão flutuante e link de dúvidas da oferta.

## Comportamento
- **VSL (hero, `#vsl`)**: player do YouTube "sem cara de YouTube" (sem controles, título, logo ou links), vídeo em `data-yt="Wvw02ExL6Ug"`, formato 9:16. Começa mudo em autoplay com o aviso "Seu vídeo já começou / Clique para ativar o som"; o clique volta ao início com som. Clique no vídeo pausa/continua. Barra de tempo fina e só visual (`fakeProg`). Mesmo player do site irmão; não trocar sem pedido explícito.
- **Sem trava** da página e sem timer: o texto abre inteiro e rola normalmente. Barra fina de progresso de leitura no topo. Seções aparecem ao rolar (`.rv`, respeita `prefers-reduced-motion`).
- **Botões `.js-cta`**: rolam até a caixa de preço (`.price-box`); só o botão da caixa de preço vai para `checkoutUrl`.
- **Caixa de preço**: "Aproveite a oferta de lançamento: de ~~R$ 197~~ por apenas R$ 127 ou 12x de R$ 13,13".
- A prévia em Artifact não carrega o YouTube (bloqueado pelo ambiente); o vídeo só aparece de verdade no site publicado.

## Rastreamento
- **Google Tag Manager**: `GTM-PJZ6Q3DW`. Eventos no `dataLayer`: `whatsapp_click`, `scroll_depth` (`scroll_percent`).
- **Meta Pixel**: `1634190808220269` (PageView) e `Scroll` (`percent` 25/50/75/100).
- **Nunca** coloque token de acesso da API de Conversões da Meta no código da página (ele fica público). Se precisar de CAPI, faça no servidor.

## Imagens
Fotos pequenas (~265×360) só servem na galeria pequena. Em destaques use fotos com ~1000px de largura.
Vídeos do Bruninho: clipes curtos, mudos, em loop, com poster `.jpg` (H.264, ~1 MB no máximo; vídeos de celular em 4K/HEVC devem ser convertidos com ffmpeg). Hoje há `web/bruninho-take.mp4` na seção "Conteúdo" (toca só quando visível). Mais clipes entram ali, no mesmo formato.

## Convenções
- Marcadores `class="todo-inline"` indicam texto pendente do cliente.
- Seções têm comentários `<!-- ===== N. NOME ===== -->`; mantenha esse padrão.
