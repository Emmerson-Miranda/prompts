# AI Prompt Documentation

Prompt to create technical specifications based on a [technical requirement analysis](../analysis/readme.md).

## Prompts

**Step 1** - Create a template document

```text
As IT software, solutions, integration, security and data architect, provide a detailed template in markdown format for creating a formal and technical design specification document for a web application, the document intended for software developers and architects. Ensure the template adheres to industry best practices, organises sections in a logical sequence, and includes a clear explanation of the purpose and expected content for each section.

Ensure you include a section for DevOps with SSDLC, CI/CD pipelines and deployment strategies to be used.

The output must be markdown.
```

Output of the previous prompt is captured in [template document](./technical_specification_template_generated.md).


**Step 2** - Create the technical specification.

```text
As IT software, solutions, integration and data architect, assist me to create a technical specification document based on the template provided.

I provided the initial analysis_generated document to give more contextual information.

Ask me clarifiying questions when needed.

The document output has to be in markdown format. Ask as many question as you need to fill up the the template.

```

Output of the previous prompt is captured in [this document](./technical_specification_generated.md).

