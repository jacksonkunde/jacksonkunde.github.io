## Guide to Setting Up and Previewing a GitHub Pages Site with Jekyll

This guide will help you set up, organize, and preview your GitHub Pages site locally using Jekyll and Homebrew’s Ruby installation. It includes steps to handle dependencies specifically for GitHub Pages.

### Step 1: Install Ruby via Homebrew

1. **Install Ruby**:
   ```bash
   brew install ruby
   ```

2. **Add Homebrew Ruby to Your PATH**:
   To ensure the terminal uses the Homebrew Ruby version, add it to your shell's PATH.

   - **For Intel Macs**:
     ```bash
     echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' >> ~/.zshrc
     ```
   
   - **For Apple Silicon (M1/M2) Macs**:
     ```bash
     echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc
     ```

3. **Reload Your Shell Profile**:
   ```bash
   source ~/.zshrc
   ```

4. **Verify the Ruby Version**:
   Run `ruby -v` to ensure Ruby 3.x or higher is active.

### Step 2: Create a `Gemfile` for GitHub Pages Dependencies

In the root of your GitHub Pages project, create a `Gemfile` with the following content to install the `github-pages` gem, which includes a compatible version of Jekyll and all necessary dependencies:

```ruby
source "https://rubygems.org"

gem "github-pages", group: :jekyll_plugins
```

This setup ensures that you’re using the same Jekyll version and dependencies as GitHub Pages, avoiding version conflicts.

### Step 3: Install Bundler and Dependencies

1. **Install Bundler**:
   ```bash
   gem install bundler
   ```

2. **Install the `github-pages` Gem**:
   ```bash
   bundle install
   ```

This command will install Jekyll and other dependencies required for GitHub Pages.

### Step 4: Preview Your Site Locally

To serve your site locally, use:

```bash
bundle exec jekyll serve
```

Visit [http://127.0.0.1:4000/](http://127.0.0.1:4000/) in your browser to preview the site.
