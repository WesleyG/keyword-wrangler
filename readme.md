to run tests:

./node_modules/.bin/jasmine-node --verbose --captureExceptions ./spec/

to make migrations:

./node_modules/.bin/db-migrate create createKeywordAndCategoryTable --env test
