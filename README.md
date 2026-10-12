<div align="center">

# HARPHiAN Control

### Feito no Brasil. Feito pra você.

**Simulador independente de robótica FTC para Windows 10 e 11 (64 bits)**

[![Windows](https://img.shields.io/badge/Windows-10%20%7C%2011-0078D6?logo=windows)](https://github.com/luizguilhermevalentinecreis-ai/Harphian-Control---Ftc-Simulator/releases)
[![Última release](https://img.shields.io/github/v/release/luizguilhermevalentinecreis-ai/Harphian-Control---Ftc-Simulator?include_prereleases&label=Release)](https://github.com/luizguilhermevalentinecreis-ai/Harphian-Control---Ftc-Simulator/releases)
[![Download](https://img.shields.io/badge/Baixar-Instalador-16a34a)](https://github.com/luizguilhermevalentinecreis-ai/Harphian-Control---Ftc-Simulator/releases)

### [⬇ BAIXAR O INSTALADOR OFICIAL](https://github.com/luizguilhermevalentinecreis-ai/Harphian-Control---Ftc-Simulator/releases)

*Built in Brazil. Made for everyone.*

</div>

---

## Conheça o HARPHiAN Control

O **HARPHiAN Control** é um simulador 3D para experimentar robótica FTC, estudar estratégias e desenvolver código Java em um ambiente virtual. Inclui arena, robôs de referência, simulação de partidas e o **Code Studio** — editor para escrever, importar e testar projetos das próprias equipes.

O simulador é um projeto independente da HARPHiAN. **Não é um produto oficial da FIRST** nem implica endosso de fabricantes ou organizações mencionados.

## Galeria do simulador

As imagens foram extraídas do vídeo de apresentação e mostram a arena 3D, sem a interface do editor.

### Visão geral da arena

![Arena BIOBUZZ](docs/screenshots/arena-overview.jpg)

### Intake e elementos da arena

![Detalhe do intake e elementos da arena](docs/screenshots/intake-and-elements.jpg)

## O que mudou na v5.4 — correção de permissões

> **Status:** a v5.4 está documentada aqui, mas só estará disponível para instalação quando o respectivo `HARPHiAN-Control-Setup-v5.4.exe` for compilado, testado e anexado a uma nova [Release](https://github.com/luizguilhermevalentinecreis-ai/Harphian-Control---Ftc-Simulator/releases). Consulte o badge acima para identificar a versão efetivamente publicada.

A atualização v5.4 trata o erro que podia impedir a inicialização em instalações dentro de `C:\Program Files\HARPHiAN Control`:

```text
java.nio.file.AccessDeniedException: C:\Program Files\HARPHiAN Control\app\data
```

**Mudanças do pacote v5.4:**

- **Dados graváveis separados do instalador:** mundos, estado e configurações são direcionados à pasta de dados do usuário em `%LOCALAPPDATA%\HARPHiAN Control\Data`.
- **Code Studio isolado por usuário:** código de cada equipe fica em `%LOCALAPPDATA%\HARPHiAN Control\TeamCode`; o ambiente de compilação fica em `%LOCALAPPDATA%\HARPHiAN Control\Workspace`.
- **Aplicativo em janela própria:** launcher Windows com ícone e visualização via WebView2, sem abrir uma aba externa do navegador.
- **WebView2 local:** o instalador final deverá incluir o *Fixed Version Runtime x64* da Microsoft para uso offline; ele precisa ser incorporado durante a compilação.
- **Porta HTTP local dinâmica:** reduz conflitos com outros programas que estejam usando a porta padrão.
- **Edição pública separada:** a distribuição não inclui o TeamCode privado, OpModes oficiais da HARPHiAN nem arquivos CAD de fabricação editáveis. Os modelos de renderização necessários à arena permanecem.

A v5.4 mantém as melhorias do **Code Studio introduzidas na v5.3**, incluindo sugestões contextuais de `import` para classes/pacotes FTC, seleção de sugestões com **Tab**, uso de **Enter** para nova linha, acionamento manual por **Ctrl + Espaço** e fechamento das sugestões ao sair do contexto.

### Situação dos testes

O pacote foi verificado em ambiente de desenvolvimento quanto a inicialização do servidor Java, salvamento de arquivos do Code Studio e execução do Build & Reload.

## Instalação (para usuários)

1. Acesse [Releases](https://github.com/luizguilhermevalentinecreis-ai/Harphian-Control---Ftc-Simulator/releases).
2. Baixe o arquivo `HARPHiAN-Control-Setup-vX.Y.exe` **anexado à versão publicada**.
3. Execute o instalador no Windows 10/11 x64 e siga as instruções.
4. Abra **HARPHiAN Control** pelo menu Iniciar ou pelo atalho criado.

**Atenção:** o ZIP de fontes de compilação **não é** o instalador para usuários finais. O instalador deve conter o Java portátil, o launcher e as dependências necessárias, incluindo o runtime WebView2 adequado à versão.

> **Segurança:** baixe sempre pela página oficial de Releases e confira o SHA-256 disponibilizado nas notas da versão.

## Atualização da versão anterior

A v5.4 instala por usuário e pode coexistir com uma instalação antiga em `Program Files`. Antes de atualizar:

- Feche o simulador.
- Faça backup de qualquer `TeamCode`, mundo ou configuração importante.
- Instale a versão nova somente após sua publicação como Release.
- Importe seu próprio projeto no Code Studio: a edição pública é distribuída **sem código das equipes**.

O novo instalador **não migra automaticamente** arquivos de projetos privados que estiverem em instalações anteriores. Se encontrar dificuldades, consulte `%LOCALAPPDATA%\HARPHiAN Control\launcher.log` e abra uma Issue com a mensagem de erro, sem dados pessoais.

## Code Studio: como começar

Abra o editor, crie um arquivo Java ou importe o ZIP com o seu projeto. Para testar as sugestões de imports, digite, por exemplo:

```java
import com.qualcomm.robotcore.hardware.Dc
```

O editor pode sugerir `DcMotor` e `DcMotorEx`. Confirme com **Tab**. **Enter** mantém o comportamento de nova linha; **Ctrl + Espaço** solicita sugestões manualmente.

O **Build & Reload** compila o código Java carregado pelo usuário, usando as APIs de simulação disponíveis. O simulador **não inclui nem distribui o código privado da HARPHiAN**.

## Distribuição e propriedade intelectual

Este repositório público disponibiliza **documentação e versões compiladas**. O código-fonte proprietário e os arquivos CAD editáveis não são publicados aqui.

As malhas utilizadas para renderização podem estar presentes no pacote de execução e continuam sujeitas às condições de uso aplicáveis. Disponibilizar esses arquivos não concede permissão de redistribuí-los ou usá-los como modelos de fabricação.

Consulte [Licença e distribuição](docs/LICENCA-E-DISTRIBUICAO.md) e as condições dos materiais de terceiros distribuídos com o aplicativo.

## Comunidade e suporte

Encontrou um bug, incompatibilidade ou sugestão para o Code Studio? [Abra uma Issue](https://github.com/luizguilhermevalentinecreis-ai/Harphian-Control---Ftc-Simulator/issues) informando a versão instalada, seu Windows e passos para reproduzir. **Não envie tokens, senhas, projetos confidenciais ou dados pessoais.**

---

<div align="center">

**HARPHiAN Control** — Feito no Brasil. Feito pra você.

</div>
