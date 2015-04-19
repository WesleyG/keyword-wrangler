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
