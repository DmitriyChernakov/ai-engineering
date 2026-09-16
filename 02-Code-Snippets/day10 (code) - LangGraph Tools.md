
Полная история сообщений, в которой находится вызов инструмента.
```Python
[
    HumanMessage(
        content="Сколько будет 25 * 48?", additional_kwargs={}, response_metadata={}
    ),
    AIMessage(
        content="",
        additional_kwargs={},
        response_metadata={
            "model": "qwen2.5:7b",
            "created_at": "2026-09-16T08:26:55.660368608Z",
            "done": True,
            "done_reason": "stop",
            "total_duration": 82171007055,
            "load_duration": 9664189095,
            "prompt_eval_count": 211,
            "prompt_eval_duration": 32851850000,
            "eval_count": 27,
            "eval_duration": 39649405000,
            "logprobs": None,
            "model_name": "qwen2.5:7b",
            "model_provider": "ollama",
        },
        id="lc_run--01a0a952-3a2f-7920-8bdd-a4b03e161fe1-0",
        tool_calls=[
            {
                "name": "multiply",
                "args": {"a": 25, "b": 48},
                "id": "84a423ae-8cd0-4416-864e-b2f80cb3a300",
                "type": "tool_call",
            }
        ],
        invalid_tool_calls=[],
        usage_metadata={"input_tokens": 211, "output_tokens": 27, "total_tokens": 238},
    ),
    ToolMessage(
        content="1200",
        name="multiply",
        tool_call_id="84a423ae-8cd0-4416-864e-b2f80cb3a300",
    ),
    AIMessage(
        content="Результат умножения 25 на 48 равен 1200.",
        additional_kwargs={},
        response_metadata={
            "model": "qwen2.5:7b",
            "created_at": "2026-09-16T08:27:21.593684902Z",
            "done": True,
            "done_reason": "stop",
            "total_duration": 25906943801,
            "load_duration": 4206784,
            "prompt_eval_count": 257,
            "prompt_eval_duration": 5470435000,
            "eval_count": 23,
            "eval_duration": 20412407000,
            "logprobs": None,
            "model_name": "qwen2.5:7b",
            "model_provider": "ollama",
        },
        id="lc_run--01a0a953-7b44-7552-8166-397bc95fb865-0",
        tool_calls=[],
        invalid_tool_calls=[],
        usage_metadata={"input_tokens": 257, "output_tokens": 23, "total_tokens": 280},
    ),
]

```
