# 🛒 Monitor da Lojinha (Web App de Monitoramento por Câmera)

Um Web App progressivo e ultraleve desenvolvido em **HTML5, JavaScript puro e Canvas**, projetado para rodar diretamente no navegador (com total compatibilidade com **GitHub Pages**) utilizando a câmera de um celular ou tablet para monitorar prateleiras e lojinhas internas.

O sistema utiliza um motor ótico otimizado de diferença de quadros para detecção de movimento em tempo real, sem dependência de redes neurais pesadas (como MediaPipe), garantindo excelente desempenho mesmo em dispositivos intermediários ou de entrada.

---

## ✨ Principais Funcionalidades

* **📐 Caixa Delimitadora 2D Ajustável:** Arraste diretamente na tela ou ajuste via menu de configuração para delimitar exatamente a área da prateleira a ser monitorada.
* **⚡ Disparo Rápido em Buffer (Burst):** Captura uma sequência configurável de fotos no exato momento da intrusão, processando os arquivos em segundo plano na memória RAM para evitar atrasos em celulares lentos.
* **🛡️ Filtro Antirreflexo e Anti-Sombra:** Sistema inteligente com compensação de luz global e rejeição de oscilação de foco automático (*focus hunting*), evitando falsos positivos causados por mudanças de iluminação ou pessoas a passar ao longe.
* **🖼️ Galeria Integrada (IndexedDB):** Armazenamento local seguro e persistente de todos os eventos capturados, com visualização em carrossel/lightbox e suporte a navegação por setas (anterior/próxima) sem precisar retornar à grelha principal.
* **💾 Zero Dependências Externas de IA:** Arquitetura front-end pura em arquivo único (`index.html`), leve, rápida e pronta para deploy instantâneo.

---

## 🚀 Como Acessar / Testar

Basta hospedar o ficheiro `index.html` em qualquer servidor estático compatível (como **GitHub Pages** ou Netlify) e abri-lo pelo navegador do celular ou tablet posicionado em frente ao local monitorado.

> **Nota de Segurança:** Para que o navegador liberte o acesso à câmara do dispositivo, a aplicação deve ser aberta preferencialmente via **HTTPS** (o GitHub Pages já fornece HTTPS nativo por defeito).

---

## ⚙️ Como Utilizar

1. **Ajustar a Área:** Com o monitoramento pausado (`▶️ Iniciar`), toque e arraste o dedo pelas bordas ou cantos da caixa verde para cobrir estritamente a prateleira.
2. **Configurar:** Clique em **⚙️ Ajustes** para calibrar a sensibilidade ao movimento, o intervalo de disparo e a quantidade de fotos por evento.
3. **Monitorar:** Clique em **▶️ Iniciar**. Quando qualquer objeto ou mão cruzar a caixa delimitada, o sistema acionará um flash visual rápido e gravará a ocorrência na galeria.
4. **Ver Registros:** Clique em **🖼️ Galeria** para inspecionar as fotos capturadas e navegar entre elas utilizando as setas laterais.

---

## 🛠️ Tecnologias Utilizadas

* **HTML5 Canvas & Video API** (Processamento de vídeo e renderização gráfica)
* **IndexedDB API** (Armazenamento local persistente de imagens e metadados)
* **JavaScript ES6+** (Motor ótico de diferença de quadros com compensação de iluminação)

---

## 📄 Licença

Este projeto está sob a licença MIT. Sinta-se livre para utilizar, modificar e adaptar para o seu estabelecimento.
