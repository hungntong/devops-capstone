# devops-capstone
aws configure set aws_session_token "key"

aws cloudformation deploy  --template-file .circleci/files/backend.yml --stack-name "capstone-backend-${CIRCLE_WORKFLOW_ID:0:7}" --parameter-overrides ID="${CIRCLE_WORKFLOW_ID:0:7}" --tags project=capstone

aws ec2 describe-instances --region us-west-2