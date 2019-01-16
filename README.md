# Vue Workshop 2019

You'll need to install a few things before starting the workshop.

### 1. Install node.js
Node.js is a standalone javascript interpreter. We'll use it to run some
development tools, including a sandbox webserver.  You can install from
[the node download site](https://nodejs.org/en/download/).

If you're using a shared Linux server, or if you want to install node in
your homedir, you can also use [nodenv](https://github.com/nodenv/nodenv).

### 2. Install yarn
Yarn is a package manager and installer like carton/cpanm. See the
[installation instructions here](https://yarnpkg.com/lang/en/docs/install).

Bash users can also just do it this way:
```
curl -o- -L https://yarnpkg.com/install.sh | bash
source ~/.bash_profile
```

### 3. Install vue
```
yarn global add @vue/cli @vue/cli-service-global
```

### 4. Verify that it works

```
git clone https://bitbucket.grantstreet.com/scm/ux/vue-workshop-2019.git
cd vue-workshop-2019
vue serve
```

Note: some Mac users are seeing that http://localhost:8080 is firewall-blocked, but http://127.0.0.1:8080 works.
