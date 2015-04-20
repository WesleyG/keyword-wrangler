#to run tests:#

./node_modules/.bin/jasmine-node --verbose --captureExceptions ./spec/

#to make migrations:#

./node_modules/.bin/db-migrate create createKeywordAndCategoryTable --env test

#applying migrations:#

./node_modules/.bin/db-migrate up --env test && \
./node_modules/.bin/jasmine-node --verbose --captureExceptions ./spec/

#log into the test sqlite db:#

sqlite3 /var/tmp/keyword-wrangler.test.sqlite

#delete the sqlite db file#
rm /var/tmp/keyword-wrangler.test.sqlite

# to run the back end #
node src/backend/index.js

# Apply migrations in dev environment
$ ./node_modules/.bin/db-migrate up --env dev
# Apply migrations in test environment
$ ./node_modules/.bin/db-migrate up --env test
# Run specs in dev environment
$ KW_ENV=dev ./node_modules/.bin/jasmine-node --verbose --captureExceptions ./sp\
ec/
# Run specs in test environment
$ KW_ENV=test ./node_modules/.bin/jasmine-node --verbose --captureExceptions ./s\
pec/
# Start server in dev environment
$ KW_ENV=dev node src/backend/index.js
# Start server in test environment
$ KW_ENV=test node src/backend/index.js
