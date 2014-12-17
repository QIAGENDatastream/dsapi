# Convenient Python Interface for Integrating with DataStream API

Collection of Python helper utilities useful for making API requests to DataStream. Key functionality include data package(s) submission and status monitoring. Built-in conveniences include automated access token refresh, multiple package handling, and HTTP connection pooling.

# INSTALLATION

type "[sudo] python setup.py install" to install for all users, or look at easy_install documentation to install in an alternate location

make sure you set environment variables like so

export ING_CLIENT_SECRET=[your client secret]

export ING_CLIENT_ID=[your client id]

# USAGE
    usage: Simple Script to Upload a zip file [-h] [--server SERVER]
    [--client-secret SECRET]
    [--client-id CLIENT_ID]
    [--logging-level LOG_LEVEL]
    file1 [file1 ...]

    python ds_upload.py t08.a.mdasnoactivate_CPCancerType_AcuteMyeloidLeukemia.zip 
    Starting to upload t08.a.mdasnoactivate_CPCancerType_AcuteMyeloidLeukemia.zip
    {u'status': u'PROCESSING', u'pipeline-name': u'Variant Analysis Cancer Pipeline', u'users': [u'mdas@ingenuity.com'], u'analysis-name': u'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.', u'title': u'MyTestID-01', u'status-url': u'https://api-stable.ingenuity.com/v1/datapackages/DP_186674283961627935264', u'warnings': [{u'message': u'r_001.txt: The field Investigation File Name is missing. We strongly recommend including this field to improve the relevance of the analysis.  This field may be required in the future.', u'code': u'isatab.recommended.field', u'details': {u'fieldname': u'Investigation File Name', u'fieldtype': u'field', u'filename': u'r_001.txt'}}], u'results-url': u'https://api-stable.ingenuity.com/datastream/analysisStatus.jsp?packageId=DP_186674283961627935264', u'percentage-complete': 40, u'creator': u'mdas@ingenuity.com', u'method': u'partner integration', u'stage': u'Loading samples'}

    usage: Simple Script to check status of package [-h] [--server SERVER]
    [--status_url STATUS_URL]
    [--dp_id DP_ID]
    [--client-secret SECRET]
    [--client-id CLIENT_ID]
    [--logging-level LOG_LEVEL]

    optional arguments:
    -h, --help            show this help message and exit
    --server SERVER       url of upload endpoint (default: https://api-
        stable.ingenuity.com/datastream/api/v1/)
        --status_url STATUS_URL
        status_url_of_package (default: None)
    --dp_id DP_ID         DP_ID of package (default: None)
        --client-secret SECRET
        supply client secret on the command line, or set an
        environment variable named ING_CLIENT_SECRET (default:
            ENV['ING_CLIENT_SECRET'])
        --client-id CLIENT_ID
        supply client id on the command, or set an environment
        variable named ING_CLIENT_ID (default:
            ENV['ING_CLIENT_ID'])
        --logging-level LOG_LEVEL
        supplying DEBUG will also start file logging for
    convenience (default: WARNING)


    python ds_status.py  --dp_id=DP_186674283961627935264
    {u'status': u'PROCESSING', u'pipeline-name': u'Variant Analysis Cancer Pipeline', u'users': [u'mdas@ingenuity.com'], u'analysis-name': u'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.', u'title': u'MyTestID-01', u'status-url': u'https://api-stable.ingenuity.com/v1/datapackages/DP_186674283961627935264', u'warnings': [{u'message': u'r_001.txt: The field Investigation File Name is missing. We strongly recommend including this field to improve the relevance of the analysis.  This field may be required in the future.', u'code': u'isatab.recommended.field', u'details': {u'fieldname': u'Investigation File Name', u'fieldtype': u'field', u'filename': u'r_001.txt'}}], u'results-url': u'https://api-stable.ingenuity.com/datastream/analysisStatus.jsp?packageId=DP_186674283961627935264', u'percentage-complete': 40, u'creator': u'mdas@ingenuity.com', u'method': u'partner integration', u'stage': u'Loading samples'}
