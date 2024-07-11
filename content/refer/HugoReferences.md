+++
title = 'Refer'
date = 2024-07-04T23:45:25+05:30
draft = true
author = 'Aravind Yamana'
+++
Hugo is a fast and flexible static site generator written in Go. It’s particularly useful for building websites and blogs. Here are some essential Hugo commands that can help you efficiently manage your Hugo projects:

Installation
Before using Hugo commands, ensure Hugo is installed on your system. You can install it using a package manager or download it directly from the Hugo releases page.

Basic Commands
Create a New Site

hugo new site <site-name>
This command initializes a new Hugo site in the specified directory.

Create a New Content File

hugo new <content-path>
For example, to create a new post:

hugo new posts/my-first-post.md
Serve the Site Locally



hugo server
This command starts a local web server and watches for changes. The default address is http://localhost:1313.

Build the Site

test

hugo
By default, this command generates the static site in the public directory.

Configuration Commands
Check Hugo Version



hugo version
This command prints the current version of Hugo.

Generate Site with Specific Config File



hugo --config <config-file>
This is useful if you have multiple configuration files and want to use a specific one.

Development Commands
List All Drafts



hugo list drafts
This command lists all draft content in your Hugo site.

Enable Drafts, Future, and Expired Content



hugo server -D
The -D flag ensures that drafts, future, and expired content are included when serving the site locally.

Clear Cache



hugo --ignoreCache
This command tells Hugo to build the site without using the cache.

Deployment Commands
Specify Output Directory



hugo -d <output-directory>
For example, to generate the site in the dist directory:



hugo -d dist
Minify Output



hugo --minify
This command generates the site with minified output for faster load times.

Advanced Commands
Profile Build Performance



hugo --templateMetrics --templateMetricints
These flags provide detailed metrics on template rendering times, which can help optimize your site's performance.

Use a Specific Theme



hugo server -t <theme-name>
This command tells Hugo to use a specific theme when serving the site locally.

Build for a Specific Environment



hugo --environment <environment>
For example, to build for a production environment:



hugo --environment production
Help Commands
Get Help on a Specific Command



hugo help <command>
For example, to get help on the new command:



hugo help new
List All Available Commands



hugo help
Summary
These commands cover the essential functionality needed to create, develop, and deploy a Hugo site. Hugo's flexibility and extensive command-line options make it a powerful tool for managing static websites. For more detailed information on each command, you can always refer to the Hugo documentation.