## Coming soon

```javascript
// Quick Example

define('lib/offline', function(require, exports, module) {
  'use strict';

  Trees = require('collections/trees');
  Cards = require('collections/cards');
  Users = require('collections/users');

  module.exports = Backbone.Offline.extend({
    paths: {
      'api/trees': {
        collection: Trees,
        resources: {
          'cards': Cards
        }
      },
      'api/users': Users
    },

    initialize: function() {
      this.on('sync:start', this.startSync, this);
      this.on('sync:end',   this.endSync, this);
    },

    startSync: function() {
      console.log('sync started');
    },

    endSync: function() {
      console.log('sync ended');
    }
  });
});

```