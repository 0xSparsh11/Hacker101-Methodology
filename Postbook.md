1.Password Brute force
- from the above step its observed that a profile named user is present
- so tired brute forcing the password for the "user" profile- Got the flag0
  
2. IDOR-1
- a profile has been created using signup page
- Later when sign in ussing the created credentials its observed that there are 2 posts already with the id displayed in the URL
- So, tried fuzzing with different ID numbers- Got flag1

3. IDOR-2
- Sign in- inspect element- we can find sub pages
- Navigate to create post- right click - inspect elements we can find below image hidden value there changed the ID to other user ID
- Created the post and submit- Got Flag2
<img width="581" height="171" alt="image" src="https://github.com/user-attachments/assets/6e31f7e3-a717-4546-a9fc-140e741ef89f" />

4. IDOR-3
- Change the ID in the URL acquired by mutliplying the give 2 numbers in the Hint-189 * 5 = XXX - Got Flag 3

5. IDOR-4 
- Navigated to edit option in the forum and observed that the ID has been used and disclosed in the inspect element
- Now changed the ID to other user ID- Got flag4
  <img width="495" height="115" alt="image" src="https://github.com/user-attachments/assets/3dec4aac-fdac-470e-a3fd-48c3a6617558" />
  <img width="1650" height="523" alt="image" src="https://github.com/user-attachments/assets/e24f7910-5002-4184-aaf9-63f104d3ff58" />

6. Cookie manipulator
- After each login, each user is assigned with a session cookie
- Inspect elements- Application-Cookie- ID: MD5 HASH
- https://10015.io/tools/md5-encrypt-decrypt using this tool encrypt and decrypt and replace the current cookie with new- Got flag5 

7. 


Reference:
- https://dev.to/caffiendkitten/ctf-postbook-2dpd 
