# Readings: React 4

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading

[Next.js - Dynamic Routes](https://nextjs.org/learn/basics/dynamic-routes)
- How to statically generate pages with dynamic routes using getStaticPaths.
- How to write getStaticProps to fetch the data for each blog post.
- How to render markdown using remark.
- How to pretty-print date strings.
- How to link to a page with dynamic routes.
- Some useful information on dynamic routes.

terminal:  routes starter  example
```
npx create-next-app nextjs-blog --use-npm --example "https://github.com/vercel/next-learn/tree/master/basics/dynamic-routes-starter"
```
You should also update the following files:

-   `public/images/profile.jpg` with your photo (Recommended: 400px width/height).
-   `const name = '[Your Name]'` in `components/layout.js` with your name.
-   `<p>[Your Self Introduction]</p>` in `pages/index.js` with your self introduction.
![](https://nextjs.org/static/images/learn/dynamic-routes/page-path-external-data.png)


![](https://nextjs.org/static/images/learn/dynamic-routes/how-to-dynamic-routes.png)


```python
export function getAllPostIds() {
  const fileNames = fs.readdirSync(postsDirectory);

  // Returns an array that looks like this:
  // [
  //   {
  //     params: {
  //       id: 'ssg-ssr'
  //     }
  //   },
  //   {
  //     params: {
  //       id: 'pre-rendering'
  //     }
  //   }
  // ]
  return fileNames.map((fileName) => {
    return {
      params: {
        id: fileName.replace(/\.md$/, ''),
      },
    };
  });
}
```

```python
import { getAllPostIds } from '../../lib/posts';

export async function getStaticPaths() {
  const paths = getAllPostIds();
  return {
    paths,
    fallback: false,
  };
}
```

```python
export function getPostData(id) {
  const fullPath = path.join(postsDirectory, `${id}.md`);
  const fileContents = fs.readFileSync(fullPath, 'utf8');

  // Use gray-matter to parse the post metadata section
  const matterResult = matter(fileContents);

  // Combine the data with the id
  return {
    id,
    ...matterResult.data,
  };
}
```

```python
import { getAllPostIds, getPostData } from '../../lib/posts';

export async function getStaticProps({ params }) {
  const postData = getPostData(params.id);
  return {
    props: {
      postData,
    },
  };
}
```

```python
export default function Post({ postData }) {
  return (
    <Layout>
      {postData.title}
      <br />
      {postData.id}
      <br />
      {postData.date}
    </Layout>
  );
}
```

And that's it :) 


[Next.js - Deployment](https://nextjs.org/learn/basics/deploying-nextjs-app)

- How to deploy your Next.js app to Vercel.
- The DPS Workflow: Develop, Preview, and Ship.
- How to deploy your Next.js app to your own hosting provider.
Use their starter code, make your repo, then deploy to vercel

Create a vercel account
import your repo
Make sure to connect any ENV variables you have so vercel knows about them


## Videos

Optional: [Next.js 10 is here](https://www.youtube.com/watch?v=JWCS5IdECVI)

## Bookmark and Review

-   [Next.js - Static File Serving](https://nextjs.org/docs/basic-features/static-file-serving)