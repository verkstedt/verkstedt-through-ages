# verkstedt.com through the ages

Created during verkstedt’s Open Wednesday 💚 and [licensed under ISC](./LICENSE).

## Running locally

```sh
npx serve .
```

## Contributing

Branches for each year are stacked on top of each other. This is to use
git history as a metaphor for the history of the HTML spec.

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