# SoundMeta-Shell 🎵

A simple interactive shell script to edit music metadata (artist, title, track number, album) using `ffmpeg`. Supports `.mp3`, `.wav`, `.ogg`, `.m4a`, and `.flac` files.

> Read this in [Portuguese (Brasil)](#-SoundMeta-Shell 🎵 (PT-BR))

---

## Features

- 🎤 Edit **artist name** — one value for all files or one-by-one confirmation
- 🎧 Edit **track title**
- 🔢 Edit **track number**
- 💿 Edit **album name** — one value for all files or one-by-one confirmation
- 🔁 **Loop mode**: edit artist, title, track number and album for each file in one pass
- ✅ Confirmation prompts before saving changes
- 🗂️ Works on all supported audio files in the current directory

## Requirements

- Bash (Linux)
- [ffmpeg](https://ffmpeg.org/) installed and available in your `PATH`

```bash
# Debian/Ubuntu
sudo apt install ffmpeg

# Arch Linux
sudo pacman -S ffmpeg
```

## Installation

```bash
git clone https://github.com/im-daxter/SoundMeta-Shell.git
cd SoundMeta-Shell
chmod +x soundmeta
```

## Usage

Navigate to the folder containing your audio files and run the script:

```bash
./soundmeta.sh
```

You'll see a menu:

```
=========================================
          MUSIC METADATA EDITOR          
=========================================
  CHOOSE AN OPTION:
-----------------------------------------
  1) Change Only Artist
  2) Change Only Title
  3) Change Only Number
  4) Change Only Album
  5) Change All in one Take
  6) Exit
=========================================
```

- **Options 1–4**: edit a single metadata field. For Artist and Album, you can choose to apply the same value to all files at once, or confirm each file individually.
- **Option 5 (Loopin Mode)**: prompts for a single album name, then walks through each file asking for track number, title, and artist, showing a summary before confirming.
- **Option 6**: exits the script.

## How it works

The script uses `ffmpeg` to rewrite metadata tags without re-encoding audio (`-c:a copy`), then replaces the original file with the updated one:

```bash
ffmpeg -i "file.mp3" -metadata artist="New Artist" -c:a copy -y "tmp_file.mp3" && mv "tmp_file.mp3" "file.mp3"
```

## ⚠️ Warning

- This script **overwrites your original files**. Make backups before running it on important music files.
- Only files matching `*.mp3 *.wav *.ogg *.m4a *.flac` in the current directory are processed.

## License

Licensed under the [GNU GPL v3.0](https://www.gnu.org/licenses/gpl-3.0.html).

## Author

**im-daxter** (Jorge Luis)

---
---

# SoundMeta-Shell 🎵 (PT-BR)

Um script shell interativo simples para editar metadados de músicas (artista, título, número da faixa, álbum) usando `ffmpeg`. Suporta arquivos `.mp3`, `.wav`, `.ogg`, `.m4a` e `.flac`.

> Read this in [English](#soundmeta-shell-)

---

## Funcionalidades

- 🎤 Editar **nome do artista** — um valor para todos os arquivos ou confirmação individual
- 🎧 Editar **título da faixa**
- 🔢 Editar **número da faixa**
- 💿 Editar **nome do álbum** — um valor para todos os arquivos ou confirmação individual
- 🔁 **Modo Loop**: edita artista, título, número da faixa e álbum de cada arquivo em uma única passagem
- ✅ Confirmação antes de salvar as alterações
- 🗂️ Funciona em todos os arquivos de áudio suportados no diretório atual

## Requisitos

- Bash (Linux/macOS/WSL)
- [ffmpeg](https://ffmpeg.org/) instalado e disponível no `PATH`

```bash
# Debian/Ubuntu
sudo apt install ffmpeg

# Arch Linux
sudo pacman -S ffmpeg
```

## Instalação

```bash
git clone https://github.com/im-daxter/SoundMeta-Shell.git
cd SoundMeta-Shell
chmod +x soundmeta
```

## Como usar

Navegue até a pasta com seus arquivos de áudio e execute o script:

```bash
./soundmeta.sh
```

Você verá um menu:

```
=========================================
          MUSIC METADATA EDITOR          
=========================================
  CHOOSE AN OPTION:
-----------------------------------------
  1) Change Only Artist
  2) Change Only Title
  3) Change Only Number
  4) Change Only Album
  5) Change All in one Take
  6) Exit
=========================================
```

- **Opções 1–4**: editam um único campo de metadado. Para Artista e Álbum, você pode aplicar o mesmo valor a todos os arquivos de uma vez, ou confirmar cada arquivo individualmente.
- **Opção 5 (Modo Loopin)**: pede o nome do álbum uma única vez, depois percorre cada arquivo pedindo número da faixa, título e artista, mostrando um resumo antes de confirmar.
- **Opção 6**: encerra o script.

## Como funciona

O script usa o `ffmpeg` para reescrever as tags de metadados sem recodificar o áudio (`-c:a copy`), substituindo o arquivo original pelo atualizado:

```bash
ffmpeg -i "arquivo.mp3" -metadata artist="Novo Artista" -c:a copy -y "tmp_arquivo.mp3" && mv "tmp_arquivo.mp3" "arquivo.mp3"
```

## ⚠️ Aviso

- Este script **sobrescreve seus arquivos originais**. Faça backup antes de executá-lo em músicas importantes.
- Apenas arquivos que correspondem a `*.mp3 *.wav *.ogg *.m4a *.flac` no diretório atual são processados.

## Licença

Licenciado sob a [GNU GPL v3.0](https://www.gnu.org/licenses/gpl-3.0.html).

## Autor

**im-daxter** (Jorge Luis)
