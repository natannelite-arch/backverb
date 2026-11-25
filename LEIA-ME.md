# Backverb Pro (VST3) — Elite Rec

Reverb reverso sincronizado ao BPM, recriado a partir do Backverb Pro v11 do Flow Music.
Parâmetros: Length, Shape, Ducking, Size, Tone, Width, Tremolo, Tremolo Speed, Low Cut, Mix, Output.

## Como gerar o .vst3 (sem instalar nada)
1. Crie uma conta grátis em github.com e um repositório novo (ex.: `backverb-pro`).
2. Envie TODOS os arquivos desta pasta (inclusive a pasta `.github`) pelo botão "Add file > Upload files".
   Dica: a pasta `.github` é oculta no Windows; se não aparecer, arraste o ZIP extraído inteiro.
3. Abra a aba **Actions**. O build roda sozinho (uns 5–10 min). Se não rodar, clique em
   "Build VST3 (Windows)" > "Run workflow".
4. Quando ficar verde, clique na execução e baixe **Backverb-Pro-VST3** (em Artifacts).
5. Extraia e copie a pasta `Backverb Pro.vst3` para `C:\Program Files\Common Files\VST3`.
6. No FL Studio: Options > Manage plugins > **Find installed plugins**. Procure "Backverb Pro" e use como efeito num canal do Mixer.

## Como funciona
O reverb grava continuamente; no fim de cada ciclo (Length) o trecho é tocado ao contrário no ciclo seguinte.
Com o play ligado ele sincroniza com a posição do projeto; parado, roda livre no BPM do host.

## Compilar localmente (opcional)
Precisa de Visual Studio 2022 (Desktop C++) e CMake: `cmake -B build` e `cmake --build build --config Release`.
