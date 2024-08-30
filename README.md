# ProfileEngage

ProfileEngage is an application designed to generate personalized icebreakers for initiating conversations on Twitter and LinkedIn. By leveraging LangChain and its components, ProfileEngage takes a person's name as input, searches for their profiles on these platforms, and crafts tailored conversation starters based on the gathered information. The project integrates multiple LangChain components and employs LangSmith for observability and performance monitoring.

## Tech Stack Used

- **Python**
- **LangChain**
- **LangSmith**
- **Proxycurl**

## Key Components

### 1. Chains
Chains were used to connect various steps in the application, including processing user input, querying APIs, and generating outputs. This seamless transition between tasks ensured efficient operation throughout the process. The application utilized the LLM to generate and structure different types of information, such as summaries, topics of interest, and icebreakers. Each function defined a specific task and set up a sequence where a prompt template was used to generate the LLM’s response. The response was then parsed and validated by the appropriate output parser, enabling flexible and reusable processing of different types of data based on user inputs.

### 2. Tools
Tools like `tavily_search` were used to query external services and extract relevant data from profiles. Other tools were employed to process URLs and extract usernames.

### 3. Agents
Agents handled tasks like searching for profiles on LinkedIn and Twitter. They made decisions based on the input and interacted with specific tools to gather and process data. CustomAgents were created to manage profile searches, defining the actions required to fetch and process LinkedIn data. This customization allowed for precise control over how profile information was retrieved.

### 4. Output Parsers
The `PydanticOutputParser` was used to parse and validate LLM outputs, converting them into structured models like `Summary` and `IceBreaker`. This ensured that the data returned by the LLM was correctly formatted and usable.

### 5. LangSmith
LangSmith was integrated to trace LLM calls, monitor tool usage, and measure performance metrics such as latency and token usage. It helped in debugging, optimizing performance, and gaining insights into the application's behavior.

