# TavaresMusic Studio Pro — macOS Beta (Intel / Apple Silicon)

Este repositório é uma cópia independente do projeto Windows, preparada para compilar dois arquivos DMG via GitHub Actions. **Ainda não foi testado em Macs reais.**

## Compilar no novo repositório
1. Envie todos os arquivos e pastas deste ZIP para a raiz do novo repositório, incluindo `.github/workflows/build-macos.yml`.
2. Abra **Actions → Build TavaresMusic macOS (Intel + Apple Silicon) → Run workflow**.
3. Aguarde os jobs Intel e AppleSilicon; baixe os artefatos de cada job.
4. Instale o DMG apropriado no Mac. O aplicativo ainda não é notarizado pela Apple, portanto pode ser bloqueado pelo Gatekeeper. Para testes, use a opção oficial **Abrir Mesmo Assim** em Ajustes do Sistema → Privacidade e Segurança, quando disponível.

## Dependências do Mac (IMPORTANTE)
Para downloads, conversões, análise de áudio e Studio DJ, instale **Homebrew** e depois rode no Terminal:

```bash
brew install ffmpeg
```

O app busca FFmpeg/FFprobe/FFplay em `/opt/homebrew/bin` (Apple Silicon) e `/usr/local/bin` (Intel), mesmo se aberto pelo Finder. **Os binários FFmpeg não são incluídos no DMG**: sua instalação é um pré-requisito desta versão experimental.

Demucs/PyTorch são empacotados pelo PyInstaller, mas ainda exigem validação funcional em ambas as arquiteturas. A primeira separação pode baixar pesos do modelo e requer conexão com a internet.

## Testes indispensáveis antes de distribuição
- Abrir o `.app` e navegar por todas as abas.
- Baixar MP3 e MP4 H.264/AAC; conferir vídeo e áudio no QuickTime.
- Reproduzir arquivos MP3 e MP4 (MP4 pode abrir em janela externa).
- Conversor WAV/MP3/FLAC, corte, fade, biblioteca e relatórios PDF.
- Studio DJ: modo Rápido e Alta Qualidade; separar voz/instrumental e quatro stems.
- DJ Playlist: BPM, tonalidade, ordenação e exportação.

## Limitações
- Builds não executados nem testados neste ambiente Linux.
- Sem assinatura Developer ID / notarização Apple; assinatura ad-hoc não substitui isso.
- O uso de FFmpeg via Homebrew torna a versão dependente de uma instalação externa.
- Versão Windows original não foi alterada.
