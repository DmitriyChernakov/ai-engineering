Функция позволяет убедиться, что инструмент был вызван
```Python
def print_tool_usage(result):
    for msg in result["messages"]:
        if getattr(msg, "tool_calls", None):
            print(f"Вызов инструмента: {msg.tool_calls[0]['name']}\n")
            return
    print("Инструмент не вызывался.\n")
```
