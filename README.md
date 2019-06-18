> run an aws-cli command in all AWS regions

## Why
Ever tried to find which region you created a thingy in? It's painful. This
tool will let you write an `aws` (CLI) command and run it against all regions.

## How to use

  1. clone the repo or download the script
  1. run the script
      ```bash
      # just replace `aws` with this script
      ./aws-all-regions lambda list-functions

      # you can specify a profile like normal
      ./aws-all-regions --profile work lambda list-functions

      # you may want to change the output so you only see what you care about
      ./aws-all-regions lambda list-functions \
        --query 'Functions[*].[FunctionName]' \
        --output text

      # we write the output to files in a temp dir, you can stop it from being
      #  cleaned up after the run. Then you can process them yourself.
      DONT_CLEANUP=1 ./aws-all-regions lambda list-functions
      ```
