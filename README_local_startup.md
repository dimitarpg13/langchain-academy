# Local startup instructions:

In a bash/zsh terminal do the following:

```bash
git clone https://github.com/langchain-ai/langchain-academy.git
cd langchain_academy
echo "TAVILY_API_KEY=\"$TAVILY_API_KEY\"" >> module-4/studio/.env
cat module-5/studio/.env
pyenv local 3.12.4
rm -rf lc-academy-env
python3 -m venv lc-academy-env
source lc-academy-env/bin/activate
pip install -r requirements.txt
cd langchain-academy
export OPENAI_API_KEY=<your-OpenAI-dev-key>
export LANGCHAIN_API_KEY=<your-LangChain-dev-key>
export LANGCHAIN_TRACING_V2=true
export TAVILY_API_KEY=<your-Tavily-Api-key>
for i in {1..6}; do
  #cp module-$i/studio/.env.example module-$i/studio/.env
  echo "OPENAI_API_KEY=\"$OPENAI_API_KEY\"" > module-$i/studio/.env
  echo "LANGCHAIN_API_KEY=\"$LANGCHAIN_API_KEY\"" > module-$i/studio/.env
  echo "LANGCHAIN_TRACING_V2=true" > module-$i/studio/.env
  echo "TAVILY_API_KEY=\"$TAVILY_API_KEY\"" > module-$i/studio/.env
done
jupyter notebook
```

In a new terminal:
```bash
cd langchain_academy
source lc-academy-env/bin/activate
cd module-1
cd studio
langgraph dev
```
