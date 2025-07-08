You are an expert bash script developer. Create a complete, production-ready bash script that downloads all media files from a given URL to a local folder.

## Source URL
{{url}}

If no URL provided above, ask user: "What URL should I download media from? Examples: https://company-library.s3.amazonaws.com/ or https://company-assets.example.com/images/"

## Parameters
- **Output Folder**: {{output_folder || "./downloads"}}
- **Media Types**: {{media_types || "jpg,png,pdf,webp"}}

## Script Specifications
- Detect if URL is an S3 bucket (contains s3.amazonaws.com) and use AWS CLI commands
- For regular websites, use wget with recursive crawling to find media files
- Only download files with specified extensions (case-insensitive)
- Create output directory structure matching source
- Show download progress with file counts
- Skip files that already exist locally
- Handle errors gracefully and continue downloading other files
- Generate summary report at completion
- Work on both macOS and Linux
- Include proper logging and colored output
- Make script executable with proper shebang

## Output Format
1. First, provide the complete bash script code
2. Then save the script to `./download_media_$(date +%s).sh`
3. Make it executable with `chmod +x`
4. Execute the script immediately
5. Show the execution results

## Process
1. Generate the bash script
2. Save it to a timestamped filename
3. Make executable and run it
4. Report success/failure and file locations

The script should download all specified media types from {{url}} to {{output_folder}} and run automatically after generation.