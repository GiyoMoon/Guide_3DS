# FAQ

::: danger

<!--@include: ./_include/3ds-online.md -->

:::

::: info

**Sim**, você ainda pode instalar custom firmware no seu 3DS, mesmo após o encerramento da eShop.

:::

## FAQ Pré-Instalação

:::details Estou na versão mais recente do sistema. É possível modificar meu console sem hardwares externos/prerequisitos?

**Sim!** New 3DS / New 3DS XL / New 2DS XL podem usar [super-skaterhax](installing-boot9strap-\(super-skaterhax\)), enquanto 3DS / 3DS XL / 2DS podem usar [MSET9](installing-boot9strap-\(mset9\)).

:::

:::details Com quais consoles este guia é compatível?

Este guia é compatível com todos os dispositivos de varejo da família 3DS (3DS, 3DS XL, 2DS, New 3DS, New 3DS XL, New 2DS XL). Se a versão de sistema é exibida como "0.0.0-0", então você pode ter uma unidade de desenvolvedor.

:::

:::details O quão arriscado é modificar meu console?

Bricks agora são efetivamente impossíveis a menos que você esteja tentando causar um brick em seu console de propósito.

:::

:::details Posso executar homebrew e emuladores incríveis com isso?

Sim! Este guia irá instalar alguns aplicativos homebrew úteis, incluindo [Universal-Updater](https://github.com/Universal-Team/Universal-Updater/releases/latest), que atua como uma loja de aplicativos homebrew.

:::

:::details Posso usar isso para jogar jogos de outras regiões?

Sim; Luma3DS irá ignorar automaticamente a verificação de região de cartuchos e aplicativos instalados. Alguns jogos podem precisar usar o [recurso de locale emulation do Luma](https://wiki.hacks.guide/wiki/3DS:Setting_game_locales) para funcionar corretamente em consoles fora da região.

:::

:::details Vou perder quaisquer recursos se eu instalar CFW?

Não. Consoles com custom firmware podem baixar as atualizações de jogos e rodar cartuchos físicos como qualquer outro 3DS pode.

:::

:::details Posso manter minha NNID, saves, jogos digitais (etc.)?

Seu NNID (se você tiver um) não será afetado por este guia. Consoles com uma região de KOR, CHN ou TWN não têm funcionalidade de NNID em primeiro lugar e portanto não são afetados.

Seguir este guia não deve resultar em perda de dados (saves, jogos digitais, etc), mas a corrupção do cartão SD é sempre uma possibilidade. Você deve fazer um backup do conteúdo do seu cartão SD se você tiver dados importantes.

:::

:::details Meu 3DS será banido por ter CFW?

Os banimentos não são mais possíveis porque os serviços da Nintendo Network foram desligados (para todos).

:::

:::details Posso fazer isso sem um computador (por exemplo, com um telefone Android)?

Na maioria dos casos, sim! O exploit MSET9 (usado principalmente para o firmware mais recente no Old 3DS) requer a execução de um script de Python ou a utilização de um aplicativo para Android, enquanto todos os outros exploits requerem apenas colocar arquivos no cartão SD.

Você pode precisar de um computador executando Windows, macOS ou Linux para reformatar seu cartão SD se ele for de 64GB ou maior.

:::

:::details Qual tamanho de cartão SD posso usar?

Você precisará de pelo menos 1.5GB de espaço livre no cartão SD para seguir este guia em sua totalidade. Enquanto o 3DS é oficialmente compatível com cartões SD de até 32GB, cartões SD maiores podem ser usados caso sejam formatados manualmente como FAT32. Não é recomendado usar cartões SD maiores que 128GB devido a problemas conhecidos com gráficos de GBA e temas personalizados.

:::

:::details Devo usar um cartão SD novo, ou o que já tenho?

Você deve usar apenas um cartão SD com um 3DS a qualquer momento. Se você usar outro cartão SD para aplicar mods em seu console, criará outro 'perfil' para o seu software com mods, que ficará inacessível no seu cartão SD original. No entanto, **seu console permanecerá com mods**, uma vez que o mod está instalado na memória interna (não no cartão SD).

Se você comprou um cartão SD novo para usar com seu console, você deve formatar o cartão SD novo ([Windows](formatting-sd-\(windows\)), [macOS](formatting-sd-\(mac\)), [Linux](formatting-sd-\(linux\))), e em seguida, copie e cole tudo do seu cartão SD antigo para o cartão SD novo. Você pode fazer isso antes ou depois de aplicar mods no console.

:::

:::details Ouvi falar sobre essa coisa que preciso comprar (Gateway, Sky3DS, ntrboot, R4, etc). Isso é algo que eu vou precisar?

Não. Enquanto um flashcart de DS pode ser utilizado para modding de um 3DS usando [ntrboot](ntrboot), agora há um novo método de software disponível para a maioria dos consoles.

Os flashcarts com 3DS-mode como Gateway e Sky3DS não são recomendados porque eles estão obsoletos e podem carregar o risco de bricks.

:::

:::details Qual a diferença entre custom firmware e homebrew?

Definitivamente falando, custom firmware refere-se a uma modificação do software do sistema 3DS para fazer coisas às quais ele normalmente não é capaz. Homebrew geralmente se refere a softwares criados fora de fontes oficiais (por exemplo, não distribuídos pela eShop ou por cartuchos).

Historicamente, o 3DS usa homebrew para acessar o homebrew de userland através de exploits mais antigos como ninjhax, que as pessoas às vezes chamaram de apenas "homebrew". O nível de acesso do sistema concedido com userland permitiu que você rodasse homebrew básico e emuladores, mas não permitia que você pudesse (facilmente) modificar jogos ou fazer dump de cartuchos. Também era muito menos estável, com o homebrew muitas vezes dando crashes indevidamente e exigindo um reinício completo. Custom firmware concede um nível muito maior de acesso ao sistema, sendo ao mesmo tempo mais estável do que pontos de entrada homebrew-only.

:::

## FAQ Pós-Instalação

:::details É seguro atualizar o meu 3DS para a versão mais recente com CFW?

Se você estiver usando o Luma3DS, o seu custom firmware loader (boot9strap) _nunca_ será removido ao executar uma atualização de sistema. Houve atualizações no passado que resultaram um crash do Luma3DS na inicialização, então é uma boa ideia esperar algumas horas para garantir que a atualização mais recente não tornará o console inutilizável temporariamente até que o Luma3DS seja atualizado. As atualizações do sistema podem ser executadas da mesma forma que em um 3DS não modificado: através da Configuração do console, Modo de Segurança, ou o aviso de atualização quando a atualização for automaticamente baixada.

:::

:::details Como faço para mudar de cartão SD?

Copie e cole o conteúdo do cartão SD em um novo cartão SD formatado como FAT32. Para cartões de 128GB, é recomendado um tamanho de alocação de 65536. Cartões SD maiores que 128GB não são recomendados devido a problemas conhecidos com gráficos de GBA e temas personalizados. Instruções específicas de formatação estão disponíveis aqui: [Windows](formatting-sd-\(windows\)), [macOS](formatting-sd-\(mac\)), [Linux](formatting-sd-\(linux\)).

:::

:::details Posso transferir meu sistema com CFW?

Sim, as transferências de sistema podem ser executadas através da função oficial de Transferência de Sistema para outros consoles com CFW (inconsistências podem ocorrer se o console de destino não for modificado). Tickets para aplicativos ilegítimos (homebrew) não transferirão, mas os aplicativos podem ser feitos para reaparecer com [faketik](https://github.com/ihaveamac/faketik/releases/latest). Certifique-se de não realizar uma transferência sem fio, pois isso excluirá os aplicativos ilegítimos. O CFW permanecerá em ambos os consoles.

:::

:::details Como altero o idioma do sistema de um 3DS japonês?

A única maneira de alterar a linguagem do sistema de um 3DS japonês para um idioma diferente do japonês é realizar uma [mudança de região](region-changing). Observe que é bem provável que isso quebre a Nintendo eShop no seu console, o que significa que você não poderá atualizar seus jogos, quer eles estejam na região ou fora da região. Você também será incapaz de acessar o Pokémon Bank (se você o tiver instalado), já que ele depende do acesso da eShop.

:::

:::details Como atualizo aplicativos homebrew?

Depende do formato do aplicativo homebrew. Geralmente:

- Aplicativos homebrew em **formato CIA** podem ser atualizados ao instalar o novo arquivo CIA, que geralmente substituirá o antigo. Se o CIA antigo não for substituído, você pode deletar o antigo através do Gerenciador de Dados como qualquer outro aplicativo de 3DS.
- Aplicativos homebrew em **formato 3DSX** podem ser atualizados substituindo o arquivo 3DSX na pasta `/3ds/` por uma nova cópia. Se o aplicativo homebrew incluir recursos adicionais, você pode precisar colocar essa pasta em outro lugar. Consulte a documentação do aplicativo homebrew.
- Para atualizar o Luma3DS, consulte [esta página](restoring-updating-cfw). Para atualizar o GodMode9, consulte [esta página](godmode9-usage#updating-godmode9).

:::

:::details Como atualizo meus jogos?

Você pode continuar baixando atualizações de jogos da Nintendo eShop, mesmo que agora tenha desligado.

Se o jogo não for da mesma região do console, você precisará [fazer um dump das atualizações](dumping-titles-and-game-cartridges) de um 3DS que tenha as atualizações instaladas. A Nintendo eShop só contém atualizações para a região do console (por exemplo, um 3DS japonês só terá atualizações para jogos japoneses).

:::

:::details Socorro! Algo ruim aconteceu e meu 3DS não inicializa mais o Menu HOME...

Por favor, veja o [guia de troubleshooting](troubleshooting-post-install). **Desinstalar CFW quando seu console está em um estado não-inicializável não é recomendado, já que é muito provável que isso leve a um brick**.

:::

## FAQ do menuhax / A9LH / Gateway

:::details Modifiquei meu console (x) anos atrás, então ele já tem algum tipo de homebrew. O que devo fazer?

É recomendável que você atualize sua configuração para um ambiente moderno e baseado em boot9strap. Siga o guia [Checando por CFW](checking-for-cfw) para ver como atualizar sua instalação.

:::

:::details Minha configuração funciona para mim. Por que eu devo atualizá-la?

A grande maioria do homebrew moderno (como Checkpoint e BootNTR Selector) foram testados apenas em um servidor moderno, em configuração baseada em boot9strap, e pode não funcionar inteiramente (ou totalmente) em instalações mais antigas baseadas em menuhax, A9LH ou Gateway. Além disso, dependendo da sua instalação, você pode ser incapaz de atualizar com segurança para o firmware mais recente. Configurações modernas e baseadas em boot9strap permitem um nível maior de acesso ao sistema do que os métodos anteriores, incluindo a capacidade fazer o dump do bootrom do seu console.

:::

:::details Vou perder alguma coisa se eu atualizar minha configuração?

A sua configuração antiga (incluindo sua EmuNAND, se você tiver uma) geralmente pode ser migrada diretamente para o boot9strap sem perda de dados. Se você tiver dados, que são particularmente importantes para você, seria uma boa ideia fazer um backup descriptografado de seus dados salvos antes de atualizar sua instalação com uma ferramenta como [JKSM](https://github.com/J-D-K/JKSM/releases/tag/12%2F20%2F2018).

:::

:::details Como posso mover saves de uma configuração existente do Gateway para uma configuração mais moderna?

Veja [este tópico](https://gbatemp.net/threads/425743/).

:::
