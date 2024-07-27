# Shell-AI: 让AI为您编写Shell命令

[![PyPI版本](https://badge.fury.io/py/shell-ai.svg)](https://pypi.org/project/shell-ai/)
[![许可证：MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![分叉](https://img.shields.io/github/forks/ricklamers/shell-ai)](https://github.com/ricklamers/shell-ai/network)
[![星标](https://img.shields.io/github/stars/ricklamers/shell-ai)](https://github.com/ricklamers/shell-ai/stargazers)


Shell-AI（`shai`）是一个命令行实用程序，将自然语言理解的能力带到您的命令行中。只需以自然语言输入您想要做的事情，`shai`将提供单行命令的建议，以实现您的意图。在幕后，Shell-AI利用[LangChain](https://github.com/langchain-ai/langchain)进行LLM使用，并在出色的[InquirerPy](https://github.com/kazhala/InquirerPy)的基础上构建交互式命令行界面。

![demo-shell-ai](https://github.com/ricklamers/shell-ai/assets/1309307/b4057165-5c23-46d4-b68e-00915b738dc3)

## 安装

您可以直接使用pip从PyPI安装Shell-AI：

- **自然语言输入**：用普通的英语（或其他支持的语言）描述您想要做的事情。
- **命令建议**：获取单行命令建议，以实现您所要求的功能。
- **跨平台**：适用于Linux、macOS和Windows。
- **Azure兼容性**：Shell-AI现在支持Azure OpenAI部署。

## Configuration
### Environment Variables

1. **`OPENAI_API_KEY`**: Required. Set this environment variable to your OpenAI API key. You can find it on your [OpenAI Dashboard](https://beta.openai.com/account/api-keys).

### Optional Variables

1. **`OPENAI_MODEL`**: Defaults to `gpt-3.5-turbo`. You can set it to another OpenAI model if desired.
2. **`SHAI_SUGGESTION_COUNT`**: Defaults to 3. You can set it to specify the number of suggestions to generate.
3. **`OPENAI_API_BASE`**: Defaults to `https://api.openai.com/v1`. You can set it to specify the proxy or service emulator.
4. **`OPENAI_ORGANIZATION`**: OpenAI Organization ID
5. **`OPENAI_PROXY`**: OpenAI proxy
6. **`OPENAI_API_TYPE`**: Set to "azure" if you are using Azure deployments.
7. **`AZURE_DEPLOYMENT_NAME`**: Your Azure deployment name (required if using Azure).
8. **`AZURE_API_BASE`**: Your Azure API base (required if using Azure).
9. **`CTX`**: Allow the assistant to keep the console outputs as context allowing the LLM to produce more precise outputs. ***IMPORTANT***: the outputs will be sent to OpenAI through their API, be careful if any sensitive data. Default to false.

You can also enable context mode in command line with `--ctx` flag:

```bash
shai --ctx [request]
```

### Configuration File

Alternatively, you can store these variables in a JSON configuration file:

- For Linux/macOS: Create a file called `config.json` under `~/.config/shell-ai/` and secure it with `chmod 600 ~/.config/shell-ai/config.json`.
- For Windows: Create a file called `config.json` under `%APPDATA%\shell-ai\`

Example `config.json`:

```json
{
  "OPENAI_API_KEY": "your_openai_api_key_here",
  "OPENAI_MODEL": "gpt-3.5-turbo",
  "SHAI_SUGGESTION_COUNT": "3",
  "CTX": true
}
```

The application will read from this file if it exists, overriding any existing environment variables.

Run the application after setting these configurations.


## Contributing

This implementation can be made much smarter! Contribute your ideas as Pull Requests and make AI Shell better for everyone.

Contributions are welcome! Please read the [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

Shell-AI is licensed under the MIT License. See [LICENSE](LICENSE) for details.
