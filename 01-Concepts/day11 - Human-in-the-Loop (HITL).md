
_HITL_ - паттерн, при котором агент останавливается перед опасным действием и ждет подтверждения человека.

## Зачем

- Безопасность
- Контроль


## Реализация в LangGraph

 - `interrupt_before=["node"]` - остановка перед нодом
 - `MemorySaver()` - чекпоинтер, сохраняет состояние после каждого `invoke`
 - `thread_id` в `config` - идентификатор сессии


## Как работает

```
invoke(msg, config) -->
загрузить state по thread_id -->
добавить новое сообщение -->
выполнить граф -->
cохранить новое состояние
```

---

##  Тесты:

```
==================================================
ТЕСТ 1: Безопасное действие (search_contacts)
==================================================
Результат: Контакт Ивана найден. Его электронная почта: ivan@example.com

==================================================
ТЕСТ 2: Опасное действие (send_email)
==================================================
Агент хочет выполнить действие:
  Tool calls: [{'name': 'send_email', 'args': {'body': 'Как дела?', 'to': 'ivan@example.com', 'subject': 'Привет'}, 'id': '732768b9-d855-460c-b688-78336db8a830', 'type': 'tool_call'}]

Подтвердить отправку? (y/n): y
Финальный результат: Email с темой "Привет" и текстом "Как дела?" успешно отправлен на ivan@example.com.
```


---
# Граф

```
graph TD;
	__start__([<p>__start__</p>]):::first
	chatbot(chatbot)
	safe_tools(safe_tools)
	dangerous_tools(dangerous_tools<hr/><small><em>__interrupt = before</em></small>)
	__end__([<p>__end__</p>]):::last
	__start__ --> chatbot;
	chatbot -.-> __end__;
	chatbot -.-> dangerous_tools;
	chatbot -.-> safe_tools;
	dangerous_tools --> chatbot;
	safe_tools --> chatbot;
	classDef default fill,line-height:1.2
	classDef first fill-opacity:1
	classDef last fill
```

![[Pasted image 20260918134659.png]]

---

# Связи
[[day08 - AI Agent (concept)]]
[[day10 - LangGraph Tools]]