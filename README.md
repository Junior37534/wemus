# Wemus Pro

![Wemus Pro](https://raw.githubusercontent.com/seu-usuario/wemus-pro/main/images/wemus-pro.jpg)

O Wemus Pro é um projeto DIY (Do It Yourself) que utiliza um display OLED 128x64 junto com um Wemos D1 Mini, criando uma interface versátil e personalizável para diversos projetos.

## 📋 Sumário

- [Características](#características)
- [Requisitos](#requisitos)
- [Hardware Necessário](#hardware-necessário)
- [Montagem](#montagem)
- [Instalação do Firmware](#instalação-do-firmware)
- [Case](#case)
- [FAQ](#faq)
- [Resolução de Problemas](#resolução-de-problemas)
- [Contribuição](#contribuição)
- [Licença](#licença)

## ✨ Características

- Display OLED 128x64 de alto contraste
- Baseado no Wemos D1 Mini (ESP8266)
- Case personalizável com corte a laser
- Interface intuitiva
- Baixo consumo de energia
- Conectividade Wi-Fi

## 📝 Requisitos

- Computador com Windows, macOS ou Linux
- Cabo USB para programação
- Maquina de corte a laser (opcional)
- Chave de fenda pequena
- Solda e ferro de soldar (básico)

## 🛠 Hardware Necessário

- 1x Wemos D1 Mini
- 1x Display OLED 128x64 I2C
- 1x Push botão de 12mm
- 6x Fios Jumpers (4x para ligar o display no Wemos e 2x para o botão)
- 1x plca MDF
- Fios para conexão
- Material para o case (acrílico ou MDF 3mm recomendado)

## 📥 Instalação do Firmware

1. Baixe o arquivo .bin mais recente da [seção de releases](https://github.com/seu-usuario/Junior37534/releases)
2. Para fazer o flash do firmware, você pode usar:
   - [ESPHome Flasher](https://github.com/esphome/esphome-flasher/releases) (Recomendado para iniciantes)
   - [ESP Flash Download Tool](https://www.espressif.com/en/support/download/other-tools)

### Instruções de Flash

1. Conecte o Wemos D1 Mini ao computador via USB
2. Abra o software de flash escolhido
3. Selecione a porta COM correta
4. Carregue o arquivo .bin
5. Inicie o processo de gravação

## 🏗 Montagem

### Conexões do Display

| Display OLED | Wemos D1 Mini |
|-------------|---------------|
| VCC         | 3.3V         |
| GND         | G (GND)      |
| SCL         | D1           |
| SDA         | D2           |

### Dicas de Montagem

- Verifique a polaridade das conexões antes de soldar
- Use fios de cores diferentes para facilitar a identificação
- Faça as conexões com o dispositivo desligado
- Teste todas as conexões antes de montar no case

## 📦 Case

O case foi projetado para ser cortado a laser em material de 3mm (acrílico ou MDF).

### Arquivos para Corte

- [soon](/files/case_tampa.svg) - Tampa superior

### Dicas para o Corte

- Verifique as dimensões antes de cortar
- Ajuste a potência do laser de acordo com o material
- Recomendamos fazer um teste em um pedaço pequeno primeiro

## ❓ FAQ

### O display não liga, o que fazer?
Verifique as conexões e certifique-se que está usando a tensão correta (3.3V).

### Posso usar outro display OLED?
Sim, desde que seja compatível com I2C e tenha resolução 128x64.

### O case pode ser impresso em 3D?
Atualmente fornecemos apenas arquivos para corte a laser, mas você pode criar sua própria versão 3D.

### Quanto tempo dura a montagem?
Com todas as peças em mãos, cerca de 30-60 minutos.

## 🔧 Resolução de Problemas

### Display mostra caracteres estranhos
- Verifique se as conexões I2C estão corretas
- Tente reflashear o firmware
- Confirme se a tensão está estável

### Não consigo fazer o flash
- Verifique se o driver USB está instalado
- Tente outro cabo USB
- Pressione o botão reset durante o processo

## 📄 Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE.md](LICENSE.md) para detalhes.

## 📞 Suporte

- Abra uma [Issue](https://github.com/seu-usuario/wemus-pro/issues)
- Entre em nosso [Discord](https://discord.gg/seu-servidor)
- Envie um email para [seu-email@dominio.com]

---

Feito com ❤️ pela comunidade maker brasileira
