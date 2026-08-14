## Flag-1 
Reflected XSS
- I suspected a XXS , so wrote a basic XSS Script "<script>alert(1)</script>" in the title field for new page creation, 
then the page got created, later when i refresherd the page the script was successful indicating the presence of Reflected XSS.

<img width="707" height="358" alt="image" src="https://github.com/user-attachments/assets/8f89b4cc-50ba-46e0-addb-b2860377abeb" />


## Flag-2 
Stored XSS
- The same above payload wasnt successfull for the comment section, because when checked for the same in the page-source- the element is scrubbed;
  so tried with different payload "<imgspacesrc="x" onerror="alert(123)">" and checked te page-source - returned the flag.  
- I tired fuzzing around with other XSS payloads, but now i was successful both in the title field and the comment section
- This is purely because of filtering and blacklist of payloads
<img width="1167" height="293" alt="image" src="https://github.com/user-attachments/assets/e35d1c2d-0618-46c7-8b5f-151df5df5a41" />

## Flag-3
IDOR
- I obsevred in the URL that every time i try navigate to new page (endpoint) the endpoint has numbers reflected in the URL.
- Later tried fuzzing using burp suite intruder - 1-100 range numbers and checked for 200 response, and checked for FLAG in the response
<img width="1548" height="847" alt="image" src="https://github.com/user-attachments/assets/02c1ed85-5924-435d-8f8f-71845b5f363f" />

Why did we checked /page/edit because https://2b84bb4042e3015ce91eb008017f652f.ctf.hacker101.com/page/7 - 403 forbidden 
<img width="1237" height="318" alt="image" src="https://github.com/user-attachments/assets/81835ca7-9506-4c67-a3cd-b40e60f7c453" />

so that we have edit options we tried navigating to the page-7 endpoint through " https://2b84bb4042e3015ce91eb008017f652f.ctf.hacker101.com**/page/edit/7** " 

## Flag-3 
SQL
Simply put a [ ' ] besides the URL : ...... ctf.hacker101.com/page/edit/12'










References:
- https://7rocky.github.io/en/ctf/hacker101ctf/micro-cms-v1/ 
- https://medium.com/@holyscotin/hacker101-ctf-micro-cms-v1-walkthrough-a7436968664c
- 
