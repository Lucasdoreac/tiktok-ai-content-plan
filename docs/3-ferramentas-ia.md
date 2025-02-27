# 3. Ferramentas de IA

Nesta etapa, configuramos e utilizamos as ferramentas de Inteligência Artificial para geração de vídeos e imagens, integrando-as ao workflow automatizado.

## Configuração do Midjourney (Imagens)

O Midjourney é um modelo gerador de imagens a partir de texto, acessível via Discord. Como não há API pública oficial do Midjourney e ele funciona através de comandos no Discord, a automação exigirá alguns passos extras:

1. Assine um plano do Midjourney e entre no servidor Discord oficial
2. Para integrar ao seu fluxo, você pode utilizar:
   - Um bot do Discord
   - Script que envie comandos `/imagine` ao bot do Midjourney com o prompt desejado
   - Download automático das imagens resultantes

Há bibliotecas e soluções comunitárias que auxiliam nisso:
- Usando a API do Discord para simular um usuário
- Controlando um navegador via Puppeteer para interagir com o Discord Web

Em termos de hardware, a geração acontece na nuvem do Midjourney, então não é necessário GPU local – apenas cuide para que seu script de automação possa receber a imagem gerada (via download do link que o bot retorna).

## Configuração do Sora (Vídeos)

Sora é o modelo de geração de vídeos da OpenAI:

- Disponível para usuários ChatGPT Plus e Pro, integrado como "Sora Turbo" sem custo adicional
- Com uma assinatura Plus, você pode gerar vídeos de até 20 segundos
- Formato vertical (9:16) com resolução até 1080p, ideal para TikTok

A geração pode ser feita via:
- Interface do ChatGPT (usando o editor de vídeo Sora)
- API (se disponível)

Para automação, prefira a API: use as credenciais da OpenAI para enviar um prompt de vídeo e receber o arquivo gerado. Caso a API do Sora ainda não esteja aberta, uma solução temporária é:
- Usar o próprio ChatGPT controlado por um script (embora menos robusto)
- Optar por ferramentas alternativas de texto-para-vídeo (como RunwayML ou Pika Labs, se possuírem API)

## Integração das Ferramentas no Fluxo

Decida como usar cada ferramenta no conteúdo do canal:

- Você pode alternar entre vídeos totalmente gerados pelo Sora e slideshows de imagens do Midjourney animados
- Uma ideia é gerar imagens no Midjourney e depois, via Sora ou edição, compô-las em um vídeo curto com transições e música

Para isso, pode ser útil um breve processamento extra:
- Usar a biblioteca de vídeo (FFmpeg, por exemplo) para montar um vídeo a partir das imagens e de um áudio trend do TikTok
- Esse processamento pode ser automatizado no seu servidor após receber as imagens do Midjourney

## Afinando Prompts e Estilos

Configure repositórios de prompts testados para agilizar a criação:

- Ferramentas de IA geram melhores resultados com prompts bem elaborados
- Mantenha um banco de prompts eficientes para diferentes situações (ex.: "arte surreal colorida", "vídeo cinemático de paisagem futurista", etc.)
- Você pode treinar a IA assistente para escolher randomicamente ou rotativamente estilos de prompt, mantendo o conteúdo variado porém dentro da estética desejada do canal

## Custos e Limites

Lembre-se dos limites das ferramentas:

- O Midjourney tem um número de gerações mensais conforme o plano
- O Sora no ChatGPT Plus tem limite de 50 vídeos (20s a 480p) por usuário em fila prioritária, embora possa gerar mais em fila relaxada

Gerencie essas quotas no planejamento de conteúdo:
- Se planeja 1 vídeo por dia, assegure-se de que seu pacote dá conta
- Tenha alternativas em stand-by (como Stable Diffusion local para imagens, ou outras plataformas de vídeo AI) caso atinja limites ou precise reduzir custos

---

**Seção anterior**: [2. Desenvolvimento e Automação](2-desenvolvimento-automacao.md)  
**Próxima seção**: [4. Expansão Multiplataforma](4-expansao-multiplataforma.md)