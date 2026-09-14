
```Python
import ollama


def ask_llm(question: str, system_prompt: str = 'Ты - полезный ассистент') -> str:
	"""Базовый вызов Ollama из Python."""
	response = ollama.chat(
		model='qwen2.5:7b',
		messages=[
			{'role': 'system', 'content': system_prompt},
			{'role': 'user', 'content': question},
		],
	)
	return response.message.content
	
# Пример использования
if __name__ == "__main__":
	answer = ask_llm("Что такое API?")
	print(answer)
```