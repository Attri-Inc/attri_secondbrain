# Attri - Your Second Brain, Empowered by Generative AI

<div align="center">
    <img src="./logo.png" alt="Attri-logo" width="30%"  style="border-radius: 50%; padding-bottom: 20px"/>
</div>

Attri, your second brain, utilizes the power of GenerativeAI to store and retrieve unstructured information. Think of it as Obsidian, but turbocharged with AI capabilities.

## Key Features 🎯

- **Universal Data Acceptance**: Attri can handle almost any type of data you throw at it. Text, images, code snippets, we've got you covered.
- **Generative AI**: Attri employs advanced AI to assist you in generating and retrieving information.
- **Fast and Efficient**: Designed with speed and efficiency at its core. Attri ensures rapid access to your data.
- **Secure**: Your data, your control. Always.
- **OS Compatible**: Ubuntu 22 or upper.
- **File Compatibility**:
  - Text
  - Markdown
  - PDF
  - Powerpoint
  - Excel (Not Yet)
  - CSV
  - Word
  - Audio
  - Video
- **Open Source**: Freedom is beautiful, and so is Attri. Open source and free to use.

### Prerequisites 📋

Ensure you have the following installed:

- Docker
- Docker Compose

- Creating a new Supabase project
- Supabase Project API key
- Supabase Project URL

### Installation Steps

- **Step 1**: Use the install helper

  You can use the install_helper.sh script to setup your env files

  ```bash
  brew install gum # Windows (via Scoop) scoop install charm-gum

  chmod +x install_helper.sh
  ./install_helper.sh
  ```

- **Step 2 - Bis**: Copy the `.XXXXX_env` files

  ```bash
  cp .backend_env.example backend/core/.env
  cp .frontend_env.example frontend/.env
  ```

- **Step 3**: Update the `backend/core/.env` and `frontend/.env` file

  > _Your `supabase_service_key` can be found in your Supabase dashboard under Project Settings -> API. Use the `anon` `public` key found in the `Project API keys` section._

  > _Your `JWT_SECRET_KEY`can be found in your supabase settings under Project Settings -> API -> JWT Settings -> JWT Secret_

  > _The `NEXT_PUBLIC_BACKEND_URL` is set to localhost:5050 for the docker. Update it if you are running the backend on a different machine._

  > _To activate vertexAI with PaLM from GCP follow the instructions [here](https://python.langchain.com/en/latest/modules/models/llms/integrations/google_vertex_ai_palm.html) and update `backend/core/.env`- It is an advanced feature, please be expert in GCP before trying to use it_

  - [ ] Change variables in `backend/core/.env`
  - [ ] Change variables in `frontend/.env`

- **Step 4**: Use the `migration.sh` script to run the migration scripts

  ```bash
  chmod +x migration.sh
  ./migration.sh
  ```

  Choose either `Create all tables` if it's your first time or `Run migrations`
  if you are updating your database.

  Alternatively you can run the script on the Supabase database via the web
  interface (SQL Editor -> `New query` -> paste the script -> `Run`)

  All the scripts can be found in the [scripts](scripts/) folder

  > _If you come from an old version of Attri, run the scripts in [migration script](scripts/) to migrate your data to the new version in the order of date_

- **Step 5**: Launch the app

  ```bash
  docker compose -f docker-compose.yml up --build
  ```

- **Step 6**: Navigate to `localhost:3000` in your browser

- **Step 7**: Want to contribute to the project?

  ```
  docker compose -f docker-compose.dev.yml up --build
  ```

## License 📄

This project is licensed under the Apache 2.0 License - see the [LICENSE](LICENSE) file for details
