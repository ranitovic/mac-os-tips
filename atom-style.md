# Customize Atom editor on Mac OS

#### Backup the original configuration
All customization can be done in ~/.atom/style.less file, so let's make a copy called ~/.atom/style-original.less
<br /><br />

#### Syntax highlight, how to know which class is displayed

Put cursor in front of the PHP keyword, then Command + Alt + P to view classes,
use the last class in the style.less to customize the syntax color
<br /><br />

#### Here is the complete style.less file

```less
// style the background color of the tree view
.tree-view {
    color: #FFFFFF;
    background-color: #1A5483;
}

.status-bar {
    color: #FFFFFF;
    background-color: #1A5483;
}

// style the background and foreground colors on the atom-text-editor-element itself
atom-text-editor.editor {
    font-size: 21px;
    color: #FFFFFF;
    background-color: #1A5483;
}

// style UI elements inside atom-text-editor
atom-text-editor .cursor {
    border-color: white;
}

@font-size: 16px;
html, body, .tree-view, .tab-bar .tab {
    font-size: @font-size;
}

.scrollbars-visible-always {
    /deep/ ::-webkit-scrollbar {
        width: 16px;
        height: 16px;

        &-track {
            border: 0px;
            border-radius: 0px;
            background-color: #1A5483 !important;
        }

        &-thumb {
            background-color: rgba(255, 255, 255, 0.7) !important;
            border: 0px;
            border-radius: 7px;
        }
    }
}

atom-text-editor {
    .gutter .line-number {
        color: #FFFFFF;
    }
}

tabs-tab, .tab {
    color: #C3C3C3 !important;
    background-color: rgba(26, 84, 131, 0.8) !important;

    &.active {
        &:before {
            border-bottom: solid 2px rgba(255, 255, 255, 0.7);
        }
        &:after {
            border-bottom: solid 2px rgba(255, 255, 255, 0.7);
        }

        background-color: rgba(26, 84, 131, 1.0) !important;
        color: #EEEEEE !important;
        border-bottom: solid 1px rgba(255, 255, 255, 0.7) !important;
    }
}

// Global Syntax Highlighting
atom-text-editor.editor
{
    .syntax--punctuation.syntax--definition.syntax--comment,
    .syntax--punctuation.syntax--comment,
    .syntax--comment, .syntax--link.syntax--hyperlink {
        color: #DDDDDD;
    }

    .syntax--link.syntax--hyperlink {
        color: #ecebbf;
    }

    .syntax--keyword.syntax--operator {
        color: #FFFFFF;
    }
}

// CSS Syntax Highlighting
atom-text-editor.editor
{
    // CSS names and tags
    .syntax--entity.syntax--name.syntax--css,
    .syntax--support.syntax--function.syntax--css {
        color: #e2b9ee;
    }

    // CSS attributes
    .syntax--entity.syntax--other.syntax--attribute-name {
        color: #ecebbf;
    }

    // CSS property names
    .syntax--support.syntax--type.syntax--property-name.syntax--css {
        color: #FFFFFF;
    }

    // CSS constants
    .syntax--constant.syntax--css,
    .syntax--support.syntax--constant.syntax--css {
        color: #98e888;
    }

    // CSS keywords
    .syntax--keyword.syntax--css {
        color: #e2b9ee;
    }

    // LESS variables
    .syntax--variable.syntax--less {
        color: #adece2;
    }
}

// PHP Syntax Highlighting
atom-text-editor.editor
{
    // PHP all source code
    .syntax--source.syntax--php {
        color: #FFFFFF;
    }

    // PHP open tag
    .syntax--punctuation.syntax--section.syntax--embedded.syntax--begin.syntax--php {
        color: #FFFFFF;
    }

    // PHP namespace
    .syntax--entity.syntax--name.syntax--type.syntax--namespace.syntax--php {
        color: #FFFFFF;
    }

    // PHP punctuation
    .syntax--punctuation,
    .syntax--punctuation.syntax--definition {
        color: #FFFFFF;
    }

    // PHP comments
    .syntax--punctuation.syntax--comment {
        color: #DDDDDD;
    }

    // PHP operators
    .syntax--keyword.syntax--operator.syntax--php {
        color: #FFFFFF;
    }

    // PHP keywords
    .syntax--keyword.syntax--php,
    .syntax--storage.syntax--php,
    .syntax--storage.syntax--modifier.syntax--php,
    .syntax--constant.syntax--language.syntax--php,
    .syntax--support.syntax--php {
        color: #e2b9ee;
    }

    // PHP constants
    .syntax--constant.syntax--php {
        color: #e6d87d;
    }

    // PHP strings
    .syntax--string.syntax--quoted.syntax--single.syntax--php,
    .syntax--string.syntax--quoted.syntax--double.syntax--php {
        color: #adece2;
    }

    // PHP numbers
    .syntax--constant.syntax--numeric.syntax--php {
        color: #98e888;
    }

    // PHP classes
    .syntax--entity.syntax--name.syntax--type.syntax--class.syntax--php {
        color: #FFFFFF;
    }

    // PHP variables and inherited classes
    .syntax--variable, .syntax--entity.syntax--other.syntax--inherited-class.syntax--php {
        color: #e6d87d;
    }

    // PHP function name
    .syntax--entity.syntax--name.syntax--function.syntax--php {
        color: #FFFFFF;
    }

    // PHP specific support classes
    .syntax--support.syntax--class.syntax--php {
        color: #FFFFFF;
    }
}

// Java Syntax Highlighting
atom-text-editor.editor
{
    // java source code
    .syntax--source.syntax--java {
        color: #FFFFFF;

        // keywords
        .syntax--keyword.syntax--other.syntax--class {
            color: #e2b9ee;
        }

        .syntax--meta.syntax--package {
            .syntax--keyword.syntax--other.syntax--package {
                color: #e2b9ee;
            }
        }

        // import packages
        .syntax--meta.syntax--import {
            color: #d4d383;
            .syntax--keyword.syntax--other.syntax--import {
                color: #e2b9ee;
            }
        }

        // storage modifier (public / private)
        .syntax--storage.syntax--modifier {
            color: #e2b9ee;
        }

        // meta.class.body
        .syntax--meta.syntax--class.syntax--body {
            color: #ecebbf;

            // numeric constant
            .syntax--constant.syntax--numeric {
                color: #ddb74f;
            }

            .syntax--storage.syntax--type {
                // color: #ddb74f;
                color: #a3d8ac;
            }

            // meta.constructor
            .syntax--meta.syntax--constructor {
                .syntax--entity.syntax--name.syntax--function {
                    color: #ecebbf;
                }

                .syntax--meta.syntax--constructor.syntax--body {
                    .syntax--variable.syntax--language {
                        color: #dfdc12;
                    }
                }
            }

            // meta.method
            .syntax--meta.syntax--method {
                color: #ecebbf;

                .syntax--entity.syntax--name.syntax--function {
                    color: #ecebbf;
                }

                // meta.method.body
                .syntax--meta.syntax--method.syntax--body {
                    color: #ecebbf;

                    // functions
                    .syntax--entity.syntax--name.syntax--function {
                        color: #ecebbf;
                    }

                    // control keywords
                    .syntax--keyword.syntax--control {
                        color: #dfdc12;
                    }

                    // numeric constant
                    .syntax--constant.syntax--numeric {
                        color: #ddb74f;
                    }

                    // boolean constant (true, false)
                    .syntax--constant.syntax--boolean {
                        color: #ddb74f;
                    }

                    // null constant
                    .syntax--constant.syntax--language.syntax--null {
                        color: #ddb74f;
                    }

                    // double quoted string
                    .syntax--string.syntax--quoted.syntax--double {
                        color: #3cd5e0;
                    }
                }
            }
        }

        // comment.block
        .syntax--comment.syntax--block {
            color: #aaaaaa;
        }

        // entity.name.type.class
        .syntax--entity.syntax--name.syntax--type.syntax--class {
            color: #dfdc12;
        }

        // storage.type
        .syntax--storage.syntax--type {
            color: #dfdc12;
        }

        // meta.declaration.annotation
        .syntax--meta.syntax--declaration.syntax--annotation {
            .syntax--string.syntax--quoted.syntax--double {
                color: #3cd5e0;
            }
        }
    }
}
```
