# TavaresMusic V1.7.0 Beta — início do suporte macOS

Base: V1.6.5 Beta. Windows mantido no workflow original.

## O que foi adaptado
- Diretório de dados macOS: `~/Library/Application Support/TavaresMusic`.
- Busca por FFmpeg em executáveis sem extensão `.exe`.
- Fallback de vídeos pelo aplicativo padrão do macOS (`open`).
- Workflow GitHub Actions separado para Mac Intel e Apple Silicon.

## Limitações importantes
- Esta é uma **primeira compilação experimental**, não uma versão macOS validada.
- O FFmpeg/FFplay instalado via Homebrew pode depender de bibliotecas dinâmicas não incorporadas ao `.app`; o empacotamento portátil ainda precisa ser resolvido e testado.
- Não há assinatura/notarização Apple; Gatekeeper pode bloquear a abertura.
- PyTorch/Demucs e codecs exigem testes reais nos dois Macs.
- Não há garantia de que os runners e dependências continuem disponíveis sem ajustes.
- Reproduzir MP4 dentro da Biblioteca (em vez de janela separada) permanece pendente.

## Próxima etapa
Executar os workflows e analisar logs dos dois jobs macOS; testar instalação, reprodução, conversão e separação de áudio nos dois chips antes de distribuir.
