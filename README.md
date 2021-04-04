# randutils
#refactor filenames
find . -type f -name "*foo*" | sed -e "p;s/foo/bar/g" | xargs -n2 mv

#refactor dirnames
find . -type d -name "*foo*" | sed -e "p;s/foo/bar/g" | xargs -n2 mv

#refactor content
grep  --exclude-dir=.git -Rl "foo" . | xargs sed -i "s/foo/bar/g"

#find all git repos and copy them
find /home/user/ -maxdepth 4 -name ".git" -type d -printf '%h\n' -prune | xargs -I@ -d"\n" cp -R @ gitrepos/

#find all zip files and copy
find /home/user/ -maxdepth 4 \( -iname '*.tar*' -o -iname '*.zip' \) -type f | xargs -I@ -d"\n" cp @ ./archives/
