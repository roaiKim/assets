

```js
(() => {
    "use strict";
    var __webpack_modules__ = ({
        "./hello.js": ((__unused_webpack_module, __webpack_exports__, __webpack_require__) => {
            __webpack_require__.r(__webpack_exports__);
            __webpack_require__.d(__webpack_exports__, {
                "default": () => (__WEBPACK_DEFAULT_EXPORT__)
            });
            const hello = "hello";
            const __WEBPACK_DEFAULT_EXPORT__ = (hello)
        }),
        "./helloworld.js": ((__unused_webpack_module, __webpack_exports__, __webpack_require__) => {
            __webpack_require__.r(__webpack_exports__);
            __webpack_require__.d(__webpack_exports__, {
                "default": () => (__WEBPACK_DEFAULT_EXPORT__)
            });
            var _hello__WEBPACK_IMPORTED_MODULE_0__ = __webpack_require__("./hello.js");
            const world = "world";
            const helloworld = () => `${_hello__WEBPACK_IMPORTED_MODULE_0__.default}${world}`;
            const __WEBPACK_DEFAULT_EXPORT__ = (helloworld)
        })
    });
    var __webpack_module_cache__ = {};

    function __webpack_require__(moduleId) {
        var cachedModule = __webpack_module_cache__[moduleId];
        if (cachedModule !== undefined) {
            return cachedModule.exports
        }
        var module = __webpack_module_cache__[moduleId] = {
            exports: {}
        };
        __webpack_modules__[moduleId](module, module.exports, __webpack_require__);
        return module.exports
    }(() => {
        __webpack_require__.d = (exports, definition) => {
            for (var key in definition) {
                if (__webpack_require__.o(definition, key) && !__webpack_require__.o(exports, key)) {
                    Object.defineProperty(exports, key, {
                        enumerable: true,
                        get: definition[key]
                    })
                }
            }
        }
    })();
    (() => {
        __webpack_require__.o = (obj, prop) => (Object.prototype.hasOwnProperty.call(obj, prop))
    })();
    (() => {
        __webpack_require__.r = (exports) => {
            if (typeof Symbol !== 'undefined' && Symbol.toStringTag) {
                Object.defineProperty(exports, Symbol.toStringTag, {
                    value: 'Module'
                })
            }
            Object.defineProperty(exports, '__esModule', {
                value: true
            })
        }
    })();
    var __webpack_exports__ = {};
    (() => {
        __webpack_require__.r(__webpack_exports__);
        var _helloworld__WEBPACK_IMPORTED_MODULE_0__ = __webpack_require__("./helloworld.js");
        const helloworldStr = (0, _helloworld__WEBPACK_IMPORTED_MODULE_0__.default)();

        function component() {
            const element = document.createElement("div") element.innerHTML = helloworldStr;
            return element
        }
        document.body.appendChild(component())
    })()
})()
```

## Symbol.toStringTag 
> 配合 Object.prototype.toString() 方法使用

```js
const obj = {}
Object.defineProperty(obj, Symbol.toStringTag, {
    value: "Module"
})
Module {Symbol(Symbol.toStringTag): "Module"}
Object.prototype.toString.call(obj)
 > "[object Module]"
Object.prototype.toString.call({})
 > "[object Object]"
```