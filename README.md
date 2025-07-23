1. Install dependencies with ´pnpm install`
2. Run the type checking on one file using `tsc`: `pnpm tsc -p tmp-tsconfig-for-git-hook.json`. You should get something like this:
   
   <img width="1268" height="268" alt="CleanShot 2025-07-23 at 18 16 19@2x" src="https://github.com/user-attachments/assets/12b5e7b4-0a57-4a18-a1db-25441895c25f" />
   
4. Run the type checking on one file using `glint`: `pnpm tsc -p tmp-tsconfig-for-git-hook.json`:

   <img width="1304" height="364" alt="CleanShot 2025-07-23 at 18 16 05@2x" src="https://github.com/user-attachments/assets/7948251f-a577-4d3c-af49-18101e529ee8" />

5. Notice how `tsc` only checks `file-with-error.ts` (since its specified under `"files"` in `tmp-tsconfig-for-git-hook.json`)
6. Glint checks `file-with-error-2.ts` even though its not referenced in `tmp-tsconfig-for-git-hook.json`. The glint command even errors out:

   <img width="1248" height="382" alt="CleanShot 2025-07-23 at 18 20 24@2x" src="https://github.com/user-attachments/assets/28131962-f31d-4148-acdc-1cc9711d3176" />

    If there is no tsconfig.json file. That should not be required since we are sending in our own config file via the -p parameter.
