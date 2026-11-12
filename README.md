# 🛒 ShelfGuard Monitor — v2.0.0 (Monitoramento Inteligente de Prateleiras)

Um **Progressive Web App (PWA)** ultraleve e 100% offline, desenvolvido em arquivo único (`index.html`) com HTML5, CSS3, JavaScript moderno e Web Workers. Projetado para rodar diretamente no navegador ou instalado na tela inicial de celulares, tablets e computadores (com total compatibilidade com **GitHub Pages**), transformando o dispositivo em um sistema inteligente de vigilância para prateleiras, balcões e pequenas lojas.

O motor ótico executa análise em tempo real de diferença de quadros e comparação de estado (*Antes × Depois*) sem depender de APIs pagas ou redes neurais pesadas, garantindo baixo consumo de bateria e alta fluidez mesmo em aparelhos intermediários.

---

## ✨ Novidades e Funcionalidades (v2.0.0)

* **📲 PWA Instalável & 100% Offline:** Conta com Manifesto dinâmico e Service Worker embutidos, permitindo instalar o aplicativo na tela inicial do celular (`standalone`) e operar sem conexão com a internet.
* **🧠 Processamento Paralelo via Web Worker:** Toda a análise de luminância, cálculo de mediana e grade espacial 5×5 roda fora da thread principal utilizando leitura vetorizada (`Uint32Array`) e troca *zero-copy* de buffers (*ping-pong*), mantendo a interface fluida.
* **🛒 Verificação Pós-Ação (Identificação de Retirada):** Compara o estado da prateleira após a saída da mão com a imagem **Base** de referência, identificando o percentual de alteração e destacando o produto retirado com uma caixa amarela (`LOCAL ALTERADO`).
* **🎯 Modo Estrito ou Completo:** Escolha entre registrar todos os movimentos (etiquetando possíveis retiradas) ou salvar **apenas** os eventos em que um produto foi efetivamente retirado.
* **⚡ Pipeline de Captura em 2 Etapas (Burst de Baixa Latência):** Captura a sequência de quadros no intervalo exato configurado sem bloquear o disparo, realizando a codificação JPEG e a geração de miniaturas leves de forma assíncrona.
* **🔋 Controle de Taxa em Vigília & Seletor de Lente:** Permite escolher exatamente qual câmera/lente traseira utilizar e ajustar os FPS de análise em repouso (padrão `10 FPS`) para reduzir o consumo de CPU e aquecimento durante horas de uso contínuo.
* **📐 Caixa Delimitadora 2D Ajustável:** Arraste ou redimensione pelas 4 bordas e 8 pontos de controle diretamente sobre o vídeo, ou calibre via controles numéricos sincronizados.
* **🖼️ Galeria Otimizada & Lightbox (IndexedDB):** Armazenamento persistente com carregamento sob demanda (*lazy loading*), miniaturas leves na grade, paginação de 20 eventos e visualização ampliada com navegação rápida.

---

## 🚀 Como Acessar, Hospedar e Instalar

1. **Hospedagem Estática:** Basta publicar o arquivo `index.html` no **GitHub Pages**, Netlify, Vercel ou servidor local (`npx serve .`).
2. **Requisito de Segurança (HTTPS):** Navegadores modernos exigem conexão segura (`HTTPS` ou `localhost`) para liberar o acesso à câmera, ao *Screen Wake Lock* e ao *Service Worker*. O GitHub Pages já fornece HTTPS nativamente.
3. **Instalar como Aplicativo (Opcional):** Ao abrir no Chrome/Edge ou Safari mobile, toque no botão **Instalar App** na barra inferior (ou em *"Adicionar à tela inicial"*) para utilizá-lo em tela cheia sem barras do navegador.

---

## ⚙️ Guia Rápido de Uso

1. **Ajustar a Área:** Com o monitoramento pausado, arraste a caixa verde pontilhada pelas bordas ou pontos de controle para cobrir exclusivamente a prateleira ou balcão desejado.
2. **Definir a Base:** Com a prateleira organizada, toque em **Base** para registrar a imagem de referência utilizada na detecção de retirada de produtos.
3. **Calibrar (Opcional):** Abra **Ajustes** para configurar a lente da câmera, taxa de FPS em vigília, sensibilidade ao movimento, tempo de espera para saída da mão, limiar de alteração (%) e modo de salvamento (*Salvar tudo* ou *Modo estrito*).
4. **Monitorar:** Toque em **Iniciar**. A caixa ficará vermelha e a tela permanecerá ativa automaticamente (*Wake Lock*). Ao detectar movimento válido, o sistema captura a rajada de fotos e verifica se houve retirada.
5. **Consultar Registros:** Toque em **Galeria** para visualizar os eventos ordenados do mais recente ao mais antigo, conferir os registros marcados como **DEPOIS** e ampliar qualquer foto no Lightbox.

---

## 🛠️ Tecnologias Utilizadas

* **HTML5 Video & Canvas API** (Renderização nativa via GPU e extração otimizada de ROI)
* **Web Workers & TypedArrays (`Uint32Array` / `Uint8Array`)** (Processamento paralelo de visão computacional)
* **IndexedDB & StorageManager API** (Persistência local de Blobs JPEG e miniaturas)
* **Service Worker & Web App Manifest** (Cache offline e instalação PWA)
* **MediaDevices & Screen Wake Lock API** (Controle de câmera e prevenção de bloqueio de tela)

---

## 📄 Licença

Este projeto está sob a licença **MIT**. Sinta-se à vontade para utilizar, modificar e adaptar para o seu estabelecimento.
