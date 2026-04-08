# mlawarereverseengineerllm
What Rellm Does
Rellm is a web-based tool that helps you safely analyze Windows program files (like .exe and .dll files) without ever running them. Think of it as an X-ray machine for software -- it looks inside files to understand what they might do, without actually executing them.

How it works:
Step 1 - Upload a File
You upload a Windows executable file (or a .md file containing existing analysis data). The tool accepts .exe, .dll, .sys, .ocx, and .md files.

Step 2 - Agent-1 (The Reader) Analyzes It
The first "agent" safely reads through the file and extracts key information:

File fingerprints (hashes like MD5, SHA256) to identify the file
File structure (sections, headers, entry point)
Imported functions -- what Windows features the program wants to use (like file access, network connections, etc.)
Strings -- readable text hidden inside the file (URLs, IP addresses, registry keys)
Entropy analysis -- measures randomness to detect if the file is packed/compressed (a common trick used by malware)
Risk score (0-100) based on suspicious patterns found
Step 3 - Agent-2 (The Explainer) Writes a Report
The second "agent" takes all that raw data and generates a human-readable security report using AI (GPT-4o-mini). If no AI key is available, it uses a built-in template instead. The report includes a summary, risk assessment, and an analyst checklist.

Key Points:
Static analysis only -- files are never executed, so it's completely safe
Educational focus -- designed with students in mind, with learning tips and friendly language
Downloadable results -- you can download the raw JSON data and the markdown report
Visual entropy chart -- shows a color-coded graph of section entropy to quickly spot suspicious patterns
It's essentially a learning tool that helps security students and analysts understand what a suspicious file might be doing before committing to deeper investigation with more advanced tools.
