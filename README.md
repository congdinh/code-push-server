# CodePush Server Selfhost

The CodePush Server is a Node.js application that powers the CodePush Service. It allows users to deploy and manage over-the-air updates for their react-native applications in a self-hosted environment.

Please refer to [react-native-code-push](https://github.com/microsoft/react-native-code-push) for instructions on how to onboard your application to CodePush.

Documents:

1. [Azure Readme](./AZURE_README.md)
2. [Codepush Readme](./CODEPUSH_README.md)
3. [Environment](./api/ENVIRONMENT.md)
4. [Security](./api/SECURITY.md)

## Setup

The CodePush CLI is a Node.js application that allows users
Download CodePush CLI

1. Clone the CodePush Service repository.
2. Install the necessary dependencies by running npm install.
3. Build the CLI by running npm run build.
4. Install CLI globally by running npm install -g.

## Authentication

Register and log in to your self-hosted CodePush server:

```
code-push-standalone register https://codepush.domain.com
code-push-standalone login https://codepush.domain.com
```

## Retrieve Deployment Information

List all deployments of an app in JSON format:

```
code-push-standalone deployment ls [app name] --format json
```

Example:

```
code-push-standalone deployment ls App_iOS --format json
```

## Retrieve Deployment History

Get the history of bundle updates for a specific deployment:

```
code-push-standalone deployment history [app name] [deployment] --format json
```

Example:

```
code-push-standalone deployment history App_Android Staging --format json
```

## Disable a Bundle Deployment by ID

Disable or enable a specific bundle version:

```
code-push-standalone patch [app name] [deployment] -l [id] --disabled [true | false]
```

Example:

```
code-push-standalone patch App_Android Production -l v5 --disabled true
```

## Change Deployment Description by ID

Update the description of a specific bundle version:

```
code-push-standalone patch [app name] [deployment] -l [id] --des [string description]
```

Example:

```
code-push-standalone patch App_Android Production -l v5 --des ""
```

## Promote a Bundle Between Deployments

Move a bundle from one deployment to another:

```
code-push-standalone promote [app name] [current deployment] [new deployment] -l [id]
```

Example:

```
code-push-standalone promote App_Android Test Staging -l v1
```

## Rollback to a Previous Version

Revert to a previous bundle version in case of issues:

```
code-push-standalone rollback [app name] [deployment] [target_label]
```

Example:

```
code-push-standalone rollback App_Android Production v4
```

## Other CLI

# Login/Register

```
code-push-standalone login https://codepush.domain.com
code-push-standalone register https://codepush.domain.com
```

# Get Deployment App

```
code-push-standalone deployment ls App_Android --format json
code-push-standalone deployment ls App_IOS --format json
```

# GET Metric

```
code-push-standalone deployment ls App_IOS --format json
```

# GET detail histories array of builds, list build packages

```
code-push-standalone deployment history App_IOS Test --format json
code-push-standalone deployment history App_Android Test --format json
```

# Mobile Deploy CLI

```
"ios-check-env": "code-push-standalone deployment ls App_IOS --format json",
"ios-update-content":"code-push-standalone patch App_IOS Test --des \"description\"",
"ios-push":"code-push-standalone release-react App_IOS ios -d Test -t 2 -p ios/App/Info.plist -o ios/build",
"ios-disabled-latest_bundle":"code-push-standalone patch App_IOS Test --disabled true"
```

# Link Mobile check latest version:

> https://codepush.domain.com/v0.1/public/codepush/update_check?deployment_key=123&app_version=2&package_hash=51934f904055eb885118c72a80ba2e6074f535cd01e824a43558fa759d1598db&label=v2&client_unique_id=C8C86AFF-4278-48DF-93B8-DCCAA6D8D16A

> https://codepush.domain.com/v0.1/public/codepush/update_check?deployment_key=123&app_version=2&client_unique_id=7296922cc0491f47
