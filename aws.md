aws s3 sync build $S3_BUCKET --delete


---------------


export VERSION=v2
node update-version
react-scripts build
aws s3 sync build $S3_BUCKET/$VERSION --delete --cache-control "public, max-age=31556926" --exclude index.html
aws s3 cp --cache-control "public, no-cache" build/index.html $S3_BUCKET

