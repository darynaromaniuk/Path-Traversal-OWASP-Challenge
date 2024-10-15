# Path-Traversal-OWASP-Challenge

## Objective 
The goal of this task was to test the ComTech marketing website for vulnerabilities, particularly focusing on a potential path traversal attack. The objective was to retrieve a hidden secret.txt file located on the web server.
## Planform: rangeforce
## Scenario
You've been tasked to test a ComTech marketing website for vulnerabilities. The website may be vulnerable to a path traversal attack on closer inspection. A secret file has been hidden on the webserver — your goal is to find the vulnerability and retrieve this file.

## Steps

<img width="572" alt="image" src="https://github.com/user-attachments/assets/2809e56a-2ef5-4137-8810-3befd282b119">

I started by navigating to the ComTech marketing website to identify potential areas where user input could be exploited.
After exploring the site, I identified a page where files were loaded by their name through URL parameters. The structure of the URL looked like this:

<img width="269" alt="image" src="https://github.com/user-attachments/assets/7fb96216-f6db-415e-8028-49ac14470864">

The **view** parameter seemed to dictate which file would be displayed, suggesting that the site might be vulnerable to path traversal. To test if the site was vulnerable, I began by inspecting how the file paths were constructed. Since the file blue.md was being retrieved from the view parameter, I hypothesized that it might be possible to manipulate this parameter to access files outside the current directory.
My goal was to access the hidden secret.txt file. Knowing that Unix-based systems allow access to parent directories using .., I decided to modify the URL and test for path traversal.

<img width="355" alt="image" src="https://github.com/user-attachments/assets/68b386ec-27f9-47e2-bcb2-f509b0b8be6f">

<img width="314" alt="image" src="https://github.com/user-attachments/assets/60a36c34-22c4-4353-b343-416d9e36fc4d">

## How I think this vulnerability can be prevented:

**Input Validation:** The website should sanitize user input to ensure file paths cannot be manipulated.
**Access Control:** Implement proper file permissions to prevent unauthorized access to sensitive directories and files.
**Ongoing Security Testing:** Regular vulnerability assessments should be conducted to identify and fix such issues.
