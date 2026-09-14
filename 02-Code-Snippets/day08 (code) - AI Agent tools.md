
```Python
TOOLS = {"calculate": calculate, "search_web": search_web}
# Тут основной код

# Модель возвращает {"tool": "calculate", "args": {"expression": "2+2"}}
result = TOOLS[action["tool"]](**action["args"])

# Результат возвращается модели как новое сообщение
messages = [  
    {"role": "assistent", "content": last_response},  
    {"role": "user", "content": f"Результат: {result}. Ответь пользователю текстом."}  
]
response = ollama.chat(model="qwen2.5:7b", messages=messages)
```