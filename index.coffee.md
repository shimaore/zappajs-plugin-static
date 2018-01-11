    path = require 'path'

    module.exports = ->
      {context,root} = this

Function for `@use`:

      @register 'static', (options) ->
        if typeof options is 'string'
          options = path: options
        options ?= {}
        p = options.path ? path.join(root, '/public')
        delete options.path
        context.express.static(p,options)

      return
