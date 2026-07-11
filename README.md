# Espetinho do Batata — Pagamentos da equipe

App simples de uma página só (`index.html`) para calcular e guardar quanto pagar
para cada funcionário freelance por dia trabalhado.

## Como rodar

Não precisa instalar nada. Duas formas:

1. **Mais simples:** dê duplo clique em `index.html` — ele abre no navegador (celular ou PC).
2. **No VS Code:** instale a extensão "Live Server", clique com o botão direito em
   `index.html` e escolha "Open with Live Server". Isso permite abrir também pelo
   celular na mesma rede Wi-Fi (o Live Server mostra o endereço, tipo `192.168.x.x:5500`).

Como é um arquivo só, também dá pra subir num serviço gratuito depois (ex: GitHub Pages,
Netlify) se quiser acessar de qualquer lugar sem depender do PC ligado.

## Regra de cálculo usada

- **Terça a quinta:** diária de R$ 60 + rateio da taxa de serviço.
- **Sexta e sábado:** diária de R$ 100 + rateio da taxa de serviço.
- **Taxa de serviço:** 10% do faturamento do dia, com 20% de imposto descontado
  (sobra 8% efetivo do faturamento), dividido em partes iguais entre todos que
  trabalharam naquele dia.
- Domingo e segunda não têm diária padrão configurada (o app avisa se você lançar
  um desses dias).

Todos esses números (diária, %, imposto) podem ser ajustados na aba **Configurações**
a qualquer momento — lançamentos antigos continuam usando a taxa que valia na época,
só os novos usam a taxa atualizada.

## Login simples

Na primeira vez que abrir, o app pede pra você criar uma senha (mínimo 4 caracteres).
Nas próximas vezes, ele pede essa senha pra entrar. Dá pra trocar a senha a qualquer
momento na aba **Configurações**, e tem um botão **Sair** no topo pra bloquear de novo.

Importante: como é um site simples, sem servidor, essa senha é só uma barreira básica
contra abertura casual — não é uma segurança forte tipo banco. Não é o tipo de proteção
adequada para dados realmente sigilosos, mas para esse uso (evitar que qualquer um mexa
nos lançamentos) já resolve.

## Onde ficam os dados

Tudo fica salvo no armazenamento local do navegador (`localStorage`), no aparelho/navegador
usado. Ou seja:

- Os dados **não somem** depois de 60 dias — ficam guardados indefinidamente, até você apagar.
- Os dados **não são compartilhados automaticamente** entre celular e computador, porque
  cada navegador guarda o seu. Para levar os dados de um aparelho pro outro, use o
  **Exportar backup** (aba Configurações) num aparelho e o **Importar backup** no outro.
- Se limpar o histórico/cache do navegador, os dados somem — por isso vale exportar um
  backup de vez em quando (é só um clique).

## Abas do app

- **Lançar dia:** escolhe a data, digita o faturamento do dia e marca quem trabalhou.
  Mostra na hora quanto cada um recebe antes de salvar.
- **Equipe:** cadastra, renomeia, desativa ou remove funcionários. Pode cadastrar
  quantos precisar.
- **Histórico:** lista todos os dias lançados, com opção de editar ou excluir.
- **Resumo mensal:** navega mês a mês e mostra quanto cada funcionário recebeu no
  total, mais o total geral pago.
- **Configurações:** ajusta os valores de diária, % de serviço e % de imposto, e
  faz backup/restauração dos dados.

## Próximos passos (se quiser evoluir depois)

- Publicar num link fixo (GitHub Pages/Netlify, grátis) pra acessar de qualquer lugar.
- Guardar os dados num banco na nuvem (ex: Firebase/Supabase, também tem plano grátis)
  pra sincronizar celular e PC automaticamente.
- Adicionar login simples se mais de uma pessoa da família for lançar dados.
