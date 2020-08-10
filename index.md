---
title: Home
has_children: true
nav_order: 1
---
## Welcome to GitHub Pages

![React Logo](https://khoshrou.github.io/AppFrame/images/react.png)

[Start Here](https://khoshrou.github.io/AppFrame/start.html)

You can use the [editor on GitHub](https://github.com/khoshrou/AppFrame/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```csharp
/// <summary>
/// GetJobromJobTitle description
/// </summary>
/// <param name="jobTitle"></param>
/// <returns></returns>
public Job GetJobromJobTitle(JobTitle jobTitle)
{F
	if (jobTitle != null)
	{
		var catid = jobTitle.JobCategory?.ID;
		if (catid != null && catid.HasValue)
		{
			return InstanceFactory<JobAtomicService>.CreateInstance(CurrentUnityContainer)
				.Get(x => x.DataStateEnum == DataStateEnum.Finalized && x.JobCategory.ID == catid);
		}
	}
	return null;
}
```

```js
import nextConnect from 'next-connect'
import auth from '../../middleware/auth'
import { deleteUser, updateUserByUsername } from '../../lib/db'

const handler = nextConnect()

handler
  .use(auth)
  .get((req, res) => {
    // You do not generally want to return the whole user object
    // because it may contain sensitive field such as !!password!! Only return what needed
    // const { name, username, favoriteColor } = req.user
    // res.json({ user: { name, username, favoriteColor } })
    res.json({ user: req.user })
  })
  .use((req, res, next) => {
    // handlers after this (PUT, DELETE) all require an authenticated user
    // This middleware to check if user is authenticated before continuing
    if (!req.user) {
      res.status(401).send('unauthenticated')
    } else {
      next()
    }
  })
  .put((req, res) => {
    const { name } = req.body
    const user = updateUserByUsername(req, req.user.username, { name })
    res.json({ user })
  })
  .delete((req, res) => {
    deleteUser(req)
    req.logOut()
    res.status(204).end()
  })

export default handler

```

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/khoshrou/AppFrame/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
