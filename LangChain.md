# LangChain Basic 

## langchain Call Ollama Model

<details>
  <summary> Click Show/Hide </summary>
  
    from langchain_ollama import ChatOllama  
    llm = ChatOllama(
        model="llama3:latest",
        base_url="http://localhost:11434",
        temperature=0.7,
        max_tokens=1000
    )

</details>

## invoke Message with LangChain

  <details>
     <summary> Click Show/Hide </summary>
    
      response = llm.invoke("what is capital of Bangladesh?")
      print(response.content)
  </details>

  
## Message Streaming with LangChain

<details>
   <summary> Click Show/Hide </summary>
  
    for chuck in  llm.stream("what is capital of India?"):
        print(chuck.content, end="", flush=True)

    for chuck in  llm.stream("How to write a simple python code to chat with ollama using langchain"):
        print(chuck.content, end="", flush=True)
</details>


## Understanding Prompt Templates

<details>
   <summary> Click Show/Hide </summary>
  
      from langchain.prompts import PromptTemplate
      prompt_template = PromptTemplate.from_template("What is the role of AI in software Engineering")
      prompt = prompt_template.invoke({})
      result = llm.invoke(prompt).content
      print(result)

</details>

## Understanding Prompt Templating for reusable Prompts

<details>
   <summary> Click Show/Hide </summary>
  
      from langchain.prompts import PromptTemplate
      prompt_template = PromptTemplate.from_template("What is the role of {type} in software Engineering")
      prompt = prompt_template.invoke({'type': 'Human'})
      print(prompt)

      result = llm.invoke(prompt).content
      print(result)
</details>

## Chaining Mechanism in LangChain

<details>
   <summary> Click Show/Hide </summary>

    from langchain.prompts import PromptTemplate
    from langchain_core.runnables import RunnableSequence
    prompt_template = PromptTemplate.from_template("What is the role of {type} in software")
    chain = RunnableSequence(prompt_template, llm)  # Pass as separate arguments
    result = chain.invoke({'type': 'AI'})
    print(result)
   
    ## Details
    from langchain.prompts import PromptTemplate
    from langchain_openai import OpenAI    
    # 1. Initialize the LLM
    # You will need to set up your API key, for example:
    # import os
    # os.environ["OPENAI_API_KEY"] = "YOUR_API_KEY"    
    # Or if you're using a free service or a different provider,
    # the initialization might look slightly different.
    # This example uses a simple OpenAI LLM.
    llm = OpenAI(model="gpt-3.5-turbo-instruct")    
    # 2. Define the prompt template
    prompt_template = PromptTemplate.from_template(
      "What is the role of {type} in software engineering?"
    )    
    # 3. Create the chain by piping the prompt to the LLM
    chain = prompt_template | llm    
    # 4. Invoke the chain with the input variable
    result = chain.invoke({'type': 'AI'})    
    # 5. Print the result
    print(result)
</details>


## Chaining with Output Parsers

<details>
  <summary> Click Show/Hide </summary>
    
    
    from langchain.prompts import PromptTemplate
    #from langchain_core.output_parsers import JsonOutputParser
    from langchain_core.output_parsers import StrOutputParser
    from langchain_core.runnables import RunnableSequence
    
    prompt_template = PromptTemplate.from_template(
    "Answer the following in JSON format: What is the role of {type} in software Engineering?"
    )
    #parser = JsonOutputParser()
    parser = StrOutputParser()  # Using StrOutputParser for simplicity
    chain = RunnableSequence(prompt_template, llm, parser)
    result = chain.invoke({'type': 'AI'})
    print(result)

    # For JsonOutputParser
    from langchain.prompts import PromptTemplate
    from langchain_core.output_parsers import JsonOutputParser
    from langchain_core.runnables import RunnableSequence
    
    prompt_template = PromptTemplate.from_template(
        "Answer the following in JSON format: What is the role of {type} in software Engineering?"
    )
    parser = JsonOutputParser()
    chain = RunnableSequence(prompt_template, llm, parser)
    result = chain.invoke({'type': 'AI'})
    print(result)

</details>



## Ref

