# Images Needed for DNP3 Timing Attack Blog Post

The DNP3 blog post requires the following screenshots to be added:

## Required Screenshots

### 1. dnp3-help.png
**Path**: `/static/images/dnp3-help.png`
**Content**: Screenshot of the DNP3 Timing Attack tool showing the help/usage information
**Command to capture**: `./dnp3-timing-attack --help` or equivalent
**Description**: Should show available command-line options, flags, and usage examples

### 2. dnp3-attack-execution.png
**Path**: `/static/images/dnp3-attack-execution.png`
**Content**: Terminal output showing the tool executing an attack
**Description**: Should show:
- Connection to target outstation
- Sending time synchronization messages
- Response from the target
- Success/error messages

### 3. dnp3-time-manipulation.png
**Path**: `/static/images/dnp3-time-manipulation.png`
**Content**: Screenshot showing the actual time manipulation in progress
**Description**: Could show:
- Before/after timestamps
- The arbitrary timestamp being sent
- Target outstation details

## How to Add Images

1. Take screenshots from your terminal using:
   - `scrot` on Linux
   - Built-in screenshot tool
   - Or any screen capture utility

2. Save images to: `/home/stephen/blogDir/hugo-site/static/images/`

3. Copy to server:
   ```bash
   scp /home/stephen/blogDir/hugo-site/static/images/dnp3-*.png blogserver:~/blog-management/hugo-site/static/images/
   ```

4. Rebuild site:
   ```bash
   ssh blogserver "cd ~/blog-management/hugo-site && ~/bin/hugo --minify"
   ```

## Tips for Good Screenshots

- Use a dark terminal theme (matches the blog aesthetic)
- Ensure text is readable (adequate font size)
- Crop out unnecessary parts
- Sanitize any sensitive information (IPs, paths, etc.)
- PNG format preferred for terminal screenshots

## Alternative: Use from GitHub

If the tool repository has screenshots, you can also reference them directly from GitHub or copy them from the repo.
