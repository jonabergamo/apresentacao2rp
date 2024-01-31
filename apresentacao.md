## Desenvolvimento front end utilizando Next.js e Tailwind css

![enter image description here](https://github.com/jonabergamo/apresentacao2rp/blob/master/imagens/imagem%2001.jpg?raw=true)

### Conceitos iniciais:

O Next.js é um framework JavaScript de código aberto que funciona em conjunto com o React para facilitar o desenvolvimento de aplicações web. Ele oferece uma camada adicional de abstração sobre o React, fornecendo funcionalidades extras para construir aplicativos web de forma eficiente.

![enter image description here](https://github.com/jonabergamo/apresentacao2rp/blob/master/imagens/Group%203078.png?raw=true)

Já o Tailwind CSS é um framework de estilo para a construção de interfaces de usuário em projetos web. Ao contrário de outros frameworks CSS que oferecem componentes pré-construídos, o Tailwind CSS adota uma abordagem diferente, fornecendo uma série de classes utilitárias que você pode aplicar diretamente nos elementos HTML para estilizar sua interface.

![enter image description here](https://github.com/jonabergamo/apresentacao2rp/blob/master/imagens/tailwind.png?raw=true)

# Comparação entre React com e sem Tailwind CSS

O desenvolvimento web moderno frequentemente envolve o uso de bibliotecas e frameworks para tornar o processo mais eficiente e agradável. React é uma biblioteca popular para construir interfaces de usuário, enquanto Tailwind CSS é um framework de estilo que oferece classes utilitárias para estilizar componentes. Vamos explorar as diferenças entre o uso de React com e sem Tailwind CSS, incluindo exemplos práticos.

### Sites que utilizam tailwind css em seu interior

1.  **Alibaba:**

    - **URL:** [Alibaba Cloud](https://www.alibabacloud.com/)
    - **Detalhes:** Alibaba Cloud, a divisão de computação em nuvem da Alibaba Group, utiliza Tailwind CSS em seu site.

2.  **GitHub:**

    - **URL:** [GitHub](https://github.com/)
    - **Detalhes:** GitHub, uma das maiores plataformas de desenvolvimento colaborativo, adotou Tailwind CSS em algumas partes de sua interface.

3.  **Trivago:**

    - **URL:** [trivago](https://www.trivago.com.br/)
    - **Detalhes:** Trivago, um popular motor de busca de hotéis, é conhecido por ter adotado Tailwind CSS em seu desenvolvimento web.
    -

## **React sem Tailwind CSS**

Ao usar React sem Tailwind CSS, os estilos geralmente são aplicados por meio de arquivos CSS ou módulos CSS. Cada componente React pode ter seu próprio arquivo de estilo, e a estilização é realizada de forma mais tradicional.

### Exemplo:

```jsx
// Componente React sem Tailwind CSS
import React from "react";
import "./Button.css";

const Button = () => {
  return <button className="custom-button">Click me</button>;
};

export default Button;
```

```css
/* Arquivo Button.css */
.custom-button {
  background-color: #3498db;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.custom-button:hover {
  background-color: #2980b9;
}
```

## **React com Tailwind CSS**

Com Tailwind CSS, a estilização é realizada diretamente nos elementos JSX usando classes utilitárias. Isso elimina a necessidade de arquivos de estilo separados e permite uma abordagem mais declarativa.

### Exemplo:

```jsx
// Componente React com Tailwind CSS
import React from "react";

const Button = () => {
  return (
    <button className="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-700">
      Click me
    </button>
  );
};

export default Button;
```

No exemplo acima, as classes como `bg-blue-500` (cor de fundo azul), `text-white` (cor do texto branca), `px-4` (padding horizontal), `py-2` (padding vertical) e `rounded` (bordas arredondadas) são fornecidas pelo Tailwind CSS.

## **Vantagens e Desvantagens**

### **React sem Tailwind CSS:**

**Vantagens:**

- Maior familiaridade para desenvolvedores acostumados com CSS convencional.

**Desvantagens:**

- Mais código e arquivos para gerenciar.
- Maior propensão a conflitos de estilo.
- O peso total dos arquivos CSS pode afetar negativamente o tempo de carregamento do site para o cliente final, impactando a experiência do usuário.

### **React com Tailwind CSS:**

**Vantagens:**

- Desenvolvimento mais rápido e menos código.
- Consistência na estilização com classes predefinidas.
- O Tailwind remove automaticamente todo o CSS não utilizado ao ser construído para produção, o que significa que seu pacote final de CSS é o menor possível. Na verdade, a maioria dos projetos que utilizam o Tailwind enviam menos de 10kB de CSS para o cliente.

### Como iniciar um projeto em Next.js

#### 1. Criar um novo projeto Next.js

```batch
npx create-next-app@latest
cd my-next-tailwind-app
```

#### 2. Responder o questionário de configuração no terminal

```batch
√ What is your project named? ... .  // Escolha um nome qualquer ou um "." para instalar na raiz.
√ Would you like to use TypeScript? ... Yes
√ Would you like to use ESLint? ... Yes
√ Would you like to use Tailwind CSS? ... Yes
√ Would you like to use `src/` directory? ... Yes
√ Would you like to use App Router? (recommended) ... Yes
√ Would you like to customize the default import alias (@/*)? ... No
```

Após o questionário as dependencias necessárias serão instaladas e o projeto será inicializado

```batch
[#########.........] | idealTree:projeto: timing idealTree:#root Completed in 41917ms
```

#### 3. Iniciar o servidor de desenvolvimento

Execute o seguinte comando para iniciar o servidor de desenvolvimento:

```batch
npm run dev
```

Acesse `http://localhost:3000` no seu navegador para ver o seu projeto Next.js com Tailwind CSS em ação!

![enter image description here](https://github.com/jonabergamo/apresentacao2rp/blob/master/imagens/first_page.png?raw=true)

No React as páginas estáticas em HTML são geradas a partir de um arquivo .jsx para javascript ou .tsx para typescript, note o x no final das extensões de arquivo, simbolizando uma extensão de arquivo especial reservada para o desenvolvimento em React.

Navegando até `app/page.tsx`, é possivel observar uma estrutura semelhante a demonstrada a baixo, onde é possivel perceber o uso prático da estilização através do tailwind css.

```jsx
import Image from "next/image";

export default function Home() {
  return (
    <main className="flex min-h-screen flex-col items-center justify-center p-8">
      {/* Seção central com imagem do Next.js */}
      <div className="relative flex place-items-center mb-8">
        {/* Imagem do Next.js */}
        <Image
          className="dark:drop-shadow-[0_0_0.3rem_#ffffff70] dark:invert"
          src="/next.svg"
          alt="Next.js Logo"
          width={180}
          height={37}
        />
      </div>

      {/* Mensagem de boas-vindas */}
      <p className="text-center text-xl mb-8">
        Get started by editing{" "}
        <code className="font-mono font-bold">app/page.tsx</code>.
      </p>

      {/* Link para a documentação */}
      <a
        href="https://nextjs.org/docs?utm_source=create-next-app&utm_medium=appdir-template&utm_campaign=create-next-app"
        className="rounded-lg border border-transparent px-5 py-4 transition-colors hover:border-gray-300 hover:bg-gray-100 hover:dark:border-neutral-700 hover:dark:bg-neutral-800/30"
        target="_blank"
        rel="noopener noreferrer">
        <h2 className="mb-2 text-2xl font-semibold">
          Docs{" "}
          <span className="inline-block transition-transform motion-reduce:transform-none">
            -&gt;
          </span>
        </h2>
        <p className="m-0 text-sm opacity-70">
          Find in-depth information about Next.js features and API.
        </p>
      </a>
    </main>
  );
}
```

`* O código acima foi resumido para fins didáticos *`
