## After researching a Lot, here are two possible ways to Setup an environment vairable.
## First method For Both Backend and Frontend
1. Install npm package `npm install dotenv`
2. This is important, on the packaged.json file add `-r dotenv/config` on the start script.
3. Then you can make an `.env` file and place vairable and access globally.
## Second method is Simple but I face that it doesnot work on nodejs backend
1. Make an `.env` file and add some Variables.
2. This is important, Name the variable starting with `REACT_APP` otherwise it doesnot work.
3. Access those file globally using `process.env.REACT_APP_FILENAME`
## Last thing make sure that you make the `.env` file on the root outside of `src` folder, otherwise it won't work!
