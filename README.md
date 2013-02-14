Source for lowerpolkneighbors.org

Generate layouts

    rake parse_haml

Generate css

    cd _scss
    compass compile

Uploading to S3

    s3cmd sync _site/ s3://www.lowerpolkneighbors.org/ --acl-public --guess-mime-type
