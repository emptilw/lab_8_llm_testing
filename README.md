# Lab 8: Testing LLM Responses in a RAG Scenario (Docker + Ollama + promptfoo)

## Environment Versions
- Docker: `ollama/ollama:0.40.16`
- Model: `qwen3:0.6b`
- Node.js: `v26.13.1`
- promptfoo: `0.121.17`

## How to Run
1. Start isolated Ollama container:
   ```bash
   docker run -d --name ollama -v ollama:/root/.ollama -p 127.0.0.1:11434:11434 --memory=2g --cpus=2 ollama/ollama:0.40.16
   ```
2. Pull the model:
   ```bash
   docker exec -it ollama ollama pull qwen3:0.6b
   ```
3. Run main RAG tests (`TC-01` – `TC-08`):
   ```bash
   npx promptfoo@0.121.17 eval
   npx promptfoo@0.121.17 view
   ```
4. Run individual task tests (`IND-01` – `IND-05`):
   ```bash
   npx promptfoo@0.121.17 eval -c promptfooconfig.individual.yaml
   ```
