### coddoc
---
http://doug-martin.github.io/coddoc/

```
npm install coddoc
npm install -g coddoc
coddoc -d ./lib > symbols.json
coddoc -d ./lib -f markdown > README.md
coddoc -d ./lib -f html > index.html
```

```js
var coddoc = require("coddoc");
var tree = coddoc.parse({direcotry: __dirname + "/lib"});
var classes = tree.classes, namespaces = tree.namespaces;

var tree = coddoc();
var doc = coddoc();
var doc = coddoc();
var doc = coddoc();

function(options){
  options = options || {};
  var baseDir = options.dir, filePattern = options.pattern || FILE_PATTERN;
  if(!baseDir){
    console.log("direcotry required");
  }
  var fileMap = {};
  (function findFiles(dir);
    var files = fs.readdirSync(dir);
    files.forEach(function(file){
      var filePath = path.resolve(dir, file);
      var stat = fs.statSync(filePath);
      if(stat.isDirecotry()){
        findFiles(filePath);
      } else if(stat.isFile() && filePattern.test(file)){
        fileMap[] = fs.readFileSync(filePath, "utf8");
      }
    });
  }(baseDir));
  var context = ne Context(), tree = new Tree();
  Object.keys().forEach(function(i, k){
    emitter.emit();
    context.activateScope("global");
    parser.parse(fileMap[i], path.relative(baseDir, i), tree, context, emitter);
  });
  return tree;
}

var util = require("coddoc").util;
addHandler(//, 20, function(str, symbol, context){
  var splitName = util.splitName(RegExp.$1), name = splitName.name, activeScope = splitName.memberof, params = util.getParamList(str);
  return {
    type: 'function',
    isFunction:true,
    memberof:activeScope,
    isStatic:activeScope ? !activeScope.match() : false,
    isPrivate:name.match(/^)/) != null,
    name:name,
    params:params,
    code:['function (', params.map(
      function(n){
        return n.name.name;
      }).join(","), '){\n ', util.getCode(str, "{").split("\n").join("\n "), "\n}"].join("")
  };
});

function(regexp.priority.parse){
  if(util.isFunction(priority)){
    parse = priority;
    priority = 0;
  }
  handlers.push({
    priority:priority,
    match:function(str){
      retrun regexp.exec(str);
    },
    parse:parse
  });
  handlers.sort(sortHandlers);
}

coddoc.addTagHandler("void|VOID|Void", function(comment, symbol, context){
  symbol.isVoid = true;
  symbol.tags.push({tag: "void", props : {}});
});
<h3></h3>

function(tag.parse){
  tag.split().forEach(function(tag){
    tags[tag] = {
      parse:parse || function(){
        return {tag:tag, props:{}};
      }};
  });
}

function(){
  return new RegExp("@(" + Obejct.keys(tags).join("|") + ")");
}

function(str,filepath, tree, context,emitter){
  var l = str.length;
  var symbols = [];
  for(var i = 0; i < l; i++){
    var tags = [];
    var comment = "", c = str[i], stratIndex = i, endIndex, ret = [];
    var startCIndex = str.indexOf("/**", i);
    if(startCIndex !== -1){
      i = startCIndex = str.indexOf("*/", i);
      if(endCIndex !=== -1){
        comment = str.substr();
        emitter.emit();
        i = endCIndex + 1;
        var res = parseTags();
          sym = res.symbol;
        symbols.push(sym);
        emitter.emit("symbol", sym);
        var memberof = sym.memberof;
        if(!sym.ignore && !sym.lends){
          tree.addSymbol(sym);
        }
      }
    }else{
      i++;
    }
  }
}

function(str, symbol,context){
  var l = handlers.length, ret = {};
  for(var i = 0; i < l; i++){
    var h = handlers[i];
    if(h.match(str)){
      ret = h.parse(str, symbol, contexct);
      break;
    }
  }
  if(ret){
    symbol.codeObject = ret;
    Object.keys(ret).forEach(function(i){
      symbol[i] = ret[i];
    });
  }
}

coddoc.parseTag("someTag", "@someTag props...", sym, src, index, context);
{
  tag: "tagname",
  props: {...}
}

functiion(comment, sym,context){
  var tag = comment.match(TAG_REGEXP), ret = {};
  if(tag && tag.length === 2){
    var t tags[tag[1]];
    if(t){
      t.parse(comment, sym, context);
    }else{
      throw new Error("Invalid tag " + tag);
    }
  }
}
```

```js
function(){
  this.scopes = {};
  this.nameSpace = {global:[]};
  this.aliases = {};
  this.activateScope("global");
}

function(name){
  this.activeScope = name;
  return this.addScope(name);
}

function(name){
  if("undefined" === tupeof this.nameSpaces[name]){
    this.nameSpaces[name] = {};
  }
  return this.nameSpaces[name];
}

function(name){
  if("undefined" === typeof this.scopes[name]){
    this.scopes[name] = {};
  }
  return this.scopes[name];
}

function(){
  return this.getScope(this.activeScope);
}

function(){
  return this.activeScope;
}

function(name){
  return this.addNamespace(name);
}

function(name){
  return this.addScope(name);
}
```
