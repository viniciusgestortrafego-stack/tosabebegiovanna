# Carta de vendas – Tosa Bebê Shih Tzu (Giovanna Rivaroli)

Página de vendas em formato de **carta de vendas escrita** (sem vídeo/VSL) do curso Tosa Bebê Shih Tzu da groomer Giovanna Rivaroli (GR Groomers, Guarulhos).
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
Site à parte, em domínio próprio na **Hostinger**, conectado a este repositório com implantação automática.
**Pendente:** definir domínio e a branch que a Hostinger publica, e registrar aqui. Mudanças: branch de trabalho → PR → merge nessa branch.

## Configuração (bloco `CONFIG` no `<script>` do fim da página)
- `checkoutUrl`: checkout da Hotmart **desta versão** (R$ 127). **Ainda vazio (pendente)**: enquanto estiver vazio, o botão da caixa de preço não leva a lugar nenhum. Usado só nesse botão; os demais botões rolam até `#oferta`.
- `whatsappUrl`: botão flutuante e link de dúvidas da oferta.

## Comportamento
Página sem trava, sem timer e sem player: abre inteira e rola normalmente. Barra fina de progresso de leitura no topo. Seções aparecem ao rolar (`.rv`, respeita `prefers-reduced-motion`).

## Rastreamento
- **Google Tag Manager**: `GTM-PJZ6Q3DW`. Eventos no `dataLayer`: `whatsapp_click`, `scroll_depth` (`scroll_percent`).
- **Meta Pixel**: `1634190808220269` (PageView) e `Scroll` (`percent` 25/50/75/100).
- **Nunca** coloque token de acesso da API de Conversões da Meta no código da página (ele fica público). Se precisar de CAPI, faça no servidor.

## Imagens
Fotos pequenas (~265×360) só servem na galeria pequena. Em destaques use fotos com ~1000px de largura.
Vídeos do Bruninho (a enviar): clipes curtos, mudos, em loop, com poster `.jpg`; entram na seção "Conteúdo" (há um comentário marcando o lugar).

## Convenções
- Marcadores `class="todo-inline"` indicam texto pendente do cliente.
- Seções têm comentários `<!-- ===== N. NOME ===== -->`; mantenha esse padrão.
