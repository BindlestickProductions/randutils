# randutils
#refactor filenames
find . -type f -name "*foo*" | sed -e "p;s/foo/bar/g" | xargs -n2 mv

#refactor dirnames
find . -type d -name "*foo*" | sed -e "p;s/foo/bar/g" | xargs -n2 mv

#refactor content
grep  --exclude-dir=.git -Rl "foo" . | xargs sed -i "s/foo/bar/g"
