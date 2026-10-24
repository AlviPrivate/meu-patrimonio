# Meu Imóvel — Design 3 revisado

Mantém a interface branca e dourada escolhida, com navegação horizontal e cartões arredondados.

## O que foi revisado

- Textos maiores, dourado com mais contraste, botões de toque maiores e campos de formulário com fonte adequada ao celular.
- No celular, a tabela de despesas se transforma em cartões com orçamento, custo final, pago, saldo, vencimento, situação e ações.
- Situações automáticas: A definir, A pagar, Parcialmente paga, Vencida, Vence hoje, Vence em até 7 dias e Quitada. Os vencimentos usam a data de Brasília.
- Filtros por unidade e situação, busca e opção de exibir todas as despesas. Exportar CSV usa as despesas que correspondem aos filtros atuais, incluindo a situação.
- A ação Quitar preenche o pago com o custo final. Para corrigir, edite a despesa.
- Lembrete de alterações sem backup e data do último backup solicitado. Nenhum arquivo é salvo em nuvem automaticamente.
- Antes de importar um backup, o site solicita confirmação e baixa uma cópia dos dados atuais. Registros inválidos podem ser baixados em sua forma original antes da recuperação.
- Proteção contra sobrescrever alterações de outra aba, datas impossíveis, pagamentos acima do custo final e valores com mais de duas casas decimais.
- Não é permitido excluir uma unidade enquanto houver despesas vinculadas a ela.

## Atualizar com segurança

1. No site atual, clique em Exportar backup e confirme que o arquivo foi baixado.
2. Extraia o ZIP e substitua o index.html na mesma pasta do repositório. O identificador do armazenamento local foi mantido.
3. Após o GitHub publicar, recarregue o site. No mesmo endereço, dispositivo e perfil de navegador, os registros continuam disponíveis.

## Entender os pagamentos

O valor Pago é acumulado; o Vencimento do saldo se refere a todo o saldo ainda aberto da despesa. Ao pagar parcelas, atualize Pago e o próximo vencimento. Esta versão não cria um histórico de parcelas. Uma despesa quitada mantém essa situação mesmo que seu vencimento tenha passado. Uma despesa sem custo final fica A definir, sem saldo inventado.

Os gráficos são acumulados por categoria e não simulam evolução mensal. Nenhuma casa, loja ou despesa de exemplo vem cadastrada.

## Verificações realizadas

Foram verificados os cálculos em centavos, as datas, as situações e filtros, cadastro, edição, exclusão, quitação, CSV, backups, restauração, recuperação e proteção entre abas por testes de regras e de funções da interface. O pacote foi compilado e validado sem dependências externas. A infraestrutura de prévia visual no navegador estava indisponível, portanto a conferência visual real no desktop e no celular permanece pendente.

## Publicar

1. Extraia este ZIP no seu computador.
2. Envie **index.html**, **README.md** e **.nojekyll** para a raiz do repositório no GitHub. Envie os arquivos extraídos, não o ZIP. Se já houver uma versão anterior, substitua o index.html antigo.
3. No repositório, abra **Settings → Pages**.
4. Em **Source**, selecione **Deploy from a branch**.
5. Selecione a branch que recebeu os arquivos (normalmente **main**) e a pasta **/(root)**. Clique em **Save**.
6. Aguarde a publicação. O endereço será exibido na mesma tela do GitHub Pages.

Instruções oficiais: https://docs.github.com/pt/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

Não exige instalação, npm, servidor, conta em outro serviço ou configuração de banco. Funciona também em repositórios de projeto, como usuario.github.io/meu-imovel/.

## Usar e guardar os registros

- Cadastre as unidades com os nomes que preferir. Nenhuma casa vem preenchida.
- Em **Compra do imóvel**, registre preço do imóvel, escritura, ITBI, registro e outros custos de aquisição.
- Em **Melhorias**, selecione uma unidade ou **Áreas comuns**.
- Informe orçamento, custo final total contratado e valor pago acumulado. Atualize o mesmo lançamento ao pagar novas parcelas para evitar contar o custo duas vezes.
- Um custo final em branco fica **A definir**. O saldo só considera custos finais informados.
- **Exportar CSV** gera uma relação das despesas.
- **Exportar backup** baixa um arquivo JSON com as unidades e despesas. **Importar backup** restaura esse arquivo, substituindo os dados atuais após confirmação.

## Como os dados são salvos

Os registros ficam no armazenamento local do navegador, no dispositivo e endereço usados. Não são enviados ao GitHub nem sincronizados com outros dispositivos. A versão hospedada anteriormente em chatgpt.site usa outro armazenamento; registros inseridos lá não são transferidos automaticamente para esta versão.

Exporte um backup regularmente e antes de limpar o navegador, trocar de computador, mudar o endereço do site ou substituir seus registros. Em navegação privada, os dados podem desaparecer ao fechar a sessão. Mantenha os backups em local seguro fora do repositório.

O GitHub Pages publica a interface do site. Não envie seus backups pessoais ao repositório. Esta versão não possui login: os dados locais podem ser acessados por quem usar o mesmo perfil de navegador.

## Arquivos

- **index.html**: aplicação completa, incluindo os estilos, ícones e código. Não depende de CDN.
- **.nojekyll**: indica que os arquivos já estão prontos para publicação.
- **README.md**: estas instruções.

Para alterar o site, mantenha uma cópia dos arquivos e substitua o index.html no repositório. Publicar o mesmo site no mesmo endereço preserva os dados locais do navegador.
