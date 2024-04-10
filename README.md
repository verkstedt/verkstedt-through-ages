# verkstedt.com through the ages

Created during verkstedt’s Open Wednesday 💚 and [licensed under ISC](./LICENSE).

## Years

- <http://1992.verkstedt.com>: HTML (Text!)
  ([code](https://github.com/verkstedt/verkstedt-through-ages/commit/1992))
- <http://1995.verkstedt.com>: HTML 2.0 (Images! Tables!)
  ([diff](https://github.com/verkstedt/verkstedt-through-ages/compare/1992...1995))
- <http://1997.verkstedt.com>: HTML 3.2 (Background images! Colours! Styles!)
  ([diff](https://github.com/verkstedt/verkstedt-through-ages/compare/1995...1997))
- (…)
- <http://2027.verkstedt.com>: I, for one, welcome our new AI overlords[^s]
  ([diff](https://github.com/verkstedt/verkstedt-through-ages/compare/1997...2027))

[^s]: https://www.youtube.com/watch?v=8lcUHQYhPTE&t=36s

## Running locally

```sh
npx serve .
```

## Contributing

Branches for each year are stacked on top of each other. This is to use
git history as a metaphor for the history of the HTML spec.
See “diff” links in [“Years” section](#years).

This means that if you want to make a change to non–latest year, you’ll
need to rebase later years on top of it. Fortunately Git makes it
(relatively) simple.

<details>

1. Make sure you have all of the year branches locally.

2. Switch to the year you want to make changes to and add new commits.

3. Switch to latest year and run:

   ```sh
   # e.g. if you changed 1992
   git rebase -i --update-refs 1992
   # inspect if everything looks ok:
   git log --oneline --decorate --all
   # push all branches:
   git push --force-with-lease --all
   ```

   For a quick explanation about `--update-refs`, check out part of
   [Scott Chacon’s “So You Think You Know Git Part 2” talk][video-update-refs].

</details>

[video-update-refs]: https://www.youtube.com/watch?v=Md44rcw13k4&t=941s

## Deploying

We deploy to Cloudflare Pages. You can use `wrangler` for that:

```sh
# preview:
npx wrangler pages deploy .
# production:
npx wrangler pages deploy --branch=main .
```
