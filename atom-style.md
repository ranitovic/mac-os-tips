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
        color: #d4a5e3;
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
        color: #FF0000;
    }

    // CSS keywords
    .syntax--keyword.syntax--css {
        color: #d4a5e3;
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
        color: #d4a5e3;
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
        color: #FF0000;
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
            color: #d4a5e3;
        }

        .syntax--meta.syntax--package {
            .syntax--keyword.syntax--other.syntax--package {
                color: #d4a5e3;
            }
        }

        // import packages
        .syntax--meta.syntax--import {
            color: #dddddd;
            .syntax--keyword.syntax--other.syntax--import {
                color: #d4a5e3;
            }
        }

        // storage modifier (public / private)
        .syntax--storage.syntax--modifier {
            color: #d4a5e3;
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
                        color: #75c9d6;
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
                color: #75c9d6;
            }
        }
    }
}

// JSP Syntax Highlighting
atom-text-editor.editor
{
    // text.html.jsp
    .syntax--text.syntax--html.syntax--jsp {
        color: #FFFFFF;

        // meta.tag.template.include.jsp
        .syntax--meta.syntax--tag.syntax--template.syntax--include.syntax--jsp {

            // keyword.control.include.jsp
            .syntax--keyword.syntax--control.syntax--include {
                color: #d6d458;
            }

            // string.quoted.double.jsp
            .syntax--string.syntax--quoted.syntax--double.syntax--jsp {
                color: #75c9d6;
            }

            // entity.other.attribute-name.jsp
            .syntax--entity.syntax--other.syntax--attribute-name.syntax--jsp {
                color: #d6d458;
            }

        }

        // meta.tag.block.h1.html
        .syntax--meta.syntax--tag.syntax--block.syntax--h1.syntax--html {

            // entity.name.tag.block.h1.html
            .syntax--entity.syntax--name.syntax--tag.syntax--block.syntax--h1.syntax--html {
                color: #78c069;
            }

            // meta.attribute-with-value.class.html
            .syntax--meta.syntax--attribute-with-value.syntax--class.syntax--html {

                // entity.other.attribute-name.class.html
                .syntax--entity.syntax--other.syntax--attribute-name.syntax--class.syntax--html {
                    color: #d4a5e3;
                }

                // string.quoted.double.html
                .syntax--string.syntax--quoted.syntax--double.syntax--html {
                    color: #75c9d6;
                }
            }
        }

        // meta.tag.block.h2.html
        .syntax--meta.syntax--tag.syntax--block.syntax--h2.syntax--html {

            // entity.name.tag.block.h2.html
            .syntax--entity.syntax--name.syntax--tag.syntax--block.syntax--h2.syntax--html {
                color: #78c069;
            }

            // meta.attribute-with-value.class.html
            .syntax--meta.syntax--attribute-with-value.syntax--class.syntax--html {

                // entity.other.attribute-name.class.html
                .syntax--entity.syntax--other.syntax--attribute-name.syntax--class.syntax--html {
                    color: #d4a5e3;
                }

                // string.quoted.double.html
                .syntax--string.syntax--quoted.syntax--double.syntax--html {
                    color: #75c9d6;
                }
            }
        }

        // meta.tag.block.h3.html
        .syntax--meta.syntax--tag.syntax--block.syntax--h3.syntax--html {

            // entity.name.tag.block.h3.html
            .syntax--entity.syntax--name.syntax--tag.syntax--block.syntax--h3.syntax--html {
                color: #78c069;
            }

            // meta.attribute-with-value.class.html
            .syntax--meta.syntax--attribute-with-value.syntax--class.syntax--html {

                // entity.other.attribute-name.class.html
                .syntax--entity.syntax--other.syntax--attribute-name.syntax--class.syntax--html {
                    color: #d4a5e3;
                }

                // string.quoted.double.html
                .syntax--string.syntax--quoted.syntax--double.syntax--html {
                    color: #75c9d6;
                }
            }
        }

        // meta.tag.block.h4.html
        .syntax--meta.syntax--tag.syntax--block.syntax--h4.syntax--html {

            // entity.name.tag.block.h4.html
            .syntax--entity.syntax--name.syntax--tag.syntax--block.syntax--h4.syntax--html {
                color: #78c069;
            }

            // meta.attribute-with-value.class.html
            .syntax--meta.syntax--attribute-with-value.syntax--class.syntax--html {

                // entity.other.attribute-name.class.html
                .syntax--entity.syntax--other.syntax--attribute-name.syntax--class.syntax--html {
                    color: #d4a5e3;
                }

                // string.quoted.double.html
                .syntax--string.syntax--quoted.syntax--double.syntax--html {
                    color: #75c9d6;
                }
            }
        }

        // meta.tag.block.h5.html
        .syntax--meta.syntax--tag.syntax--block.syntax--h5.syntax--html {

            // entity.name.tag.block.h5.html
            .syntax--entity.syntax--name.syntax--tag.syntax--block.syntax--h5.syntax--html {
                color: #78c069;
            }

            // meta.attribute-with-value.class.html
            .syntax--meta.syntax--attribute-with-value.syntax--class.syntax--html {

                // entity.other.attribute-name.class.html
                .syntax--entity.syntax--other.syntax--attribute-name.syntax--class.syntax--html {
                    color: #d4a5e3;
                }

                // string.quoted.double.html
                .syntax--string.syntax--quoted.syntax--double.syntax--html {
                    color: #75c9d6;
                }
            }
        }

        // meta.tag.block.h6.html
        .syntax--meta.syntax--tag.syntax--block.syntax--h6.syntax--html {

            // entity.name.tag.block.h6.html
            .syntax--entity.syntax--name.syntax--tag.syntax--block.syntax--h6.syntax--html {
                color: #78c069;
            }

            // meta.attribute-with-value.class.html
            .syntax--meta.syntax--attribute-with-value.syntax--class.syntax--html {

                // entity.other.attribute-name.class.html
                .syntax--entity.syntax--other.syntax--attribute-name.syntax--class.syntax--html {
                    color: #d4a5e3;
                }

                // string.quoted.double.html
                .syntax--string.syntax--quoted.syntax--double.syntax--html {
                    color: #75c9d6;
                }
            }
        }

        // meta.tag.block.div.html
        .syntax--meta.syntax--tag.syntax--block.syntax--div.syntax--html {

            // meta.attribute-with-value.class.html
            .syntax--meta.syntax--attribute-with-value.syntax--class.syntax--html {

                // entity.other.attribute-name.class.html
                .syntax--entity.syntax--other.syntax--attribute-name.syntax--class.syntax--html {
                    color: #d4a5e3;
                }

                // string.quoted.double.html
                .syntax--string.syntax--quoted.syntax--double.syntax--html {
                    color: #75c9d6;
                }
            }

            // entity.name.tag.block.div.html
            .syntax--entity.syntax--name.syntax--tag.syntax--block.syntax--div.syntax--html {
                color: #d6d458;
            }
        }

        // meta.tag.block.ul.html
        .syntax--meta.syntax--tag.syntax--block.syntax--ul.syntax--html {

            // meta.attribute-with-value.class.html
            .syntax--meta.syntax--attribute-with-value.syntax--class.syntax--html {

                // entity.other.attribute-name.class.html
                .syntax--entity.syntax--other.syntax--attribute-name.syntax--class.syntax--html {
                    color: #d4a5e3;
                }

                // string.quoted.double.html
                .syntax--string.syntax--quoted.syntax--double.syntax--html {
                    color: #75c9d6;
                }
            }

            // entity.name.tag.block.ul.html
            .syntax--entity.syntax--name.syntax--tag.syntax--block.syntax--ul.syntax--html {
                color: #78c069;
            }
        }

        // meta.tag.inline.a.html
        .syntax--meta.syntax--tag.syntax--inline.syntax--a.syntax--html {
            // entity.name.tag.inline.a.html
            .syntax--entity.syntax--name.syntax--tag.syntax--inline.syntax--a.syntax--html {
                color: #78c069;
            }
            // string.quoted.double.html
            .syntax--string.syntax--quoted.syntax--double.syntax--html {
                color: #75c9d6;
            }

            // meta.attribute-with-value.html
            .syntax--meta.syntax--attribute-with-value.syntax--html {
                // entity.other.attribute-name.html
                .syntax--entity.syntax--other.syntax--attribute-name.syntax--html {
                    color: #78c069;
                }
            }

            // meta.attribute-with-value.class
            .syntax--meta.syntax--attribute-with-value.syntax--class {
                // entity.other.attribute-name.class.html
                .syntax--entity.syntax--other.syntax--attribute-name.syntax--class.syntax--html {
                    color: #d4a5e3;
                }
            }
        }

        // meta.tag.inline.b.html
        .syntax--meta.syntax--tag.syntax--inline.syntax--b.syntax--html {
            // entity.name.tag.inline.b.html
            .syntax--entity.syntax--name.syntax--tag.syntax--inline.syntax--b.syntax--html {
                color: #78c069;
            }

            // entity.other.attribute-name.class.html
            .syntax--entity.syntax--other.syntax--attribute-name.syntax--class.syntax--html {
                color: #d4a5e3;
            }

            // string.quoted.double.html
            .syntax--string.syntax--quoted.syntax--double.syntax--html {
                color: #75c9d6;
            }
        }

        // meta.tag.inline.i.html
        .syntax--meta.syntax--tag.syntax--inline.syntax--i.syntax--html {
            // entity.name.tag.inline.i.html
            .syntax--entity.syntax--name.syntax--tag.syntax--inline.syntax--i.syntax--html {
                color: #78c069;
            }

            // entity.other.attribute-name.class.html
            .syntax--entity.syntax--other.syntax--attribute-name.syntax--class.syntax--html {
                color: #d4a5e3;
            }

            // string.quoted.double.html
            .syntax--string.syntax--quoted.syntax--double.syntax--html {
                color: #75c9d6;
            }
        }

        // meta.tag.inline.img.html
        .syntax--meta.syntax--tag.syntax--inline.syntax--img.syntax--html {
            // entity.name.tag.inline.img.html
            .syntax--entity.syntax--name.syntax--tag.syntax--inline.syntax--img.syntax--html {
                color: #78c069;
            }

            // entity.other.attribute-name.class.html
            .syntax--entity.syntax--other.syntax--attribute-name.syntax--class.syntax--html {
                color: #d4a5e3;
            }

            // string.quoted.double.html
            .syntax--string.syntax--quoted.syntax--double.syntax--html {
                color: #75c9d6;
            }
        }

        // meta.tag.inline.li.html
        .syntax--meta.syntax--tag.syntax--inline.syntax--li.syntax--html {
            // entity.name.tag.inline.li.html
            .syntax--entity.syntax--name.syntax--tag.syntax--inline.syntax--li.syntax--html {
                color: #78c069;
            }

            // entity.other.attribute-name.class.html
            .syntax--entity.syntax--other.syntax--attribute-name.syntax--class.syntax--html {
                color: #d4a5e3;
            }

            // string.quoted.double.html
            .syntax--string.syntax--quoted.syntax--double.syntax--html {
                color: #75c9d6;
            }
        }

        // meta.tag.inline.option.html
        .syntax--meta.syntax--tag.syntax--inline.syntax--option.syntax--html {
            // entity.name.tag.inline.option.html
            .syntax--entity.syntax--name.syntax--tag.syntax--inline.syntax--option.syntax--html {
                color: #78c069;
            }

            // string.quoted.single.html
            .syntax--string.syntax--quoted.syntax--single.syntax--html {
                color: #75c9d6;
            }

            // meta.attribute-with-value.html
            .syntax--meta.syntax--attribute-with-value.syntax--html {
                color: #FFFFFF;

                // string.quoted.double.html
                .syntax--string.syntax--quoted.syntax--double.syntax--html {
                    color: #75c9d6;
                }

                // punctuation.separator.key-value.html
                .syntax--punctuation.syntax--separator.syntax--key-value.syntax--html {
                    color: #FFFFFF;
                }

            }

            // entity.other.attribute-name.html
            .syntax--entity.syntax--other.syntax--attribute-name.syntax--html {
                color: #78c069;
            }
        }

        // meta.tag.inline.select.html
        .syntax--meta.syntax--tag.syntax--inline.syntax--select.syntax--html {
            // entity.name.tag.inline.select.html
            .syntax--entity.syntax--name.syntax--tag.syntax--inline.syntax--select.syntax--html {
                color: #78c069;
            }

            // meta.attribute-with-value.class.html
            .syntax--meta.syntax--attribute-with-value.syntax--class.syntax--html {

                // entity.other.attribute-name.class.html
                .syntax--entity.syntax--other.syntax--attribute-name.syntax--class.syntax--html {
                    color: #d4a5e3;
                }

                // string.quoted.double.html
                .syntax--string.syntax--quoted.syntax--double.syntax--html {
                    color: #75c9d6;
                }
            }

            // meta.attribute-with-value.id.html
            .syntax--meta.syntax--attribute-with-value.syntax--id.syntax--html {
                // entity.other.attribute-name.id.html
                .syntax--entity.syntax--other.syntax--attribute-name.syntax--id.syntax--html {
                    color: #78c069;
                }

                // string.quoted.double.html
                .syntax--string.syntax--quoted.syntax--double.syntax--html {
                    color: #FFFFFF;
                }
            }
        }

        // meta.tag.inline.span.html
        .syntax--meta.syntax--tag.syntax--inline.syntax--span.syntax--html {
            // entity.name.tag.inline.span.html
            .syntax--entity.syntax--name.syntax--tag.syntax--inline.syntax--span.syntax--html {
                color: #78c069;
            }

            // entity.other.attribute-name.class.html
            .syntax--entity.syntax--other.syntax--attribute-name.syntax--class.syntax--html {
                color: #d4a5e3;
            }

            // string.quoted.double.html
            .syntax--string.syntax--quoted.syntax--double.syntax--html {
                color: #75c9d6;
            }
        }

        // meta.embedded.line.el_expression.jsp
        .syntax--meta.syntax--embedded.syntax--line.syntax--el_expression.syntax--jsp {
            // punctuation.section.embedded.begin.jsp
            .syntax--punctuation.syntax--section.syntax--embedded.syntax--begin {
                color: #e68f48;
            }

            // punctuation.section.embedded.end.jsp
            .syntax--punctuation.syntax--section.syntax--embedded.syntax--end {
                // source.java
                .syntax--source.syntax--java {
                    color: #dba36f;
                }
            }

            // source.java
            .syntax--source.syntax--java {
                // string.quoted.single.java.el
                .syntax--string.syntax--quoted.syntax--single.syntax--java.syntax--el {
                    color: #75c9d6;
                }

                // constant.numeric.java.el
                .syntax--constant.syntax--numeric.syntax--java.syntax--el {
                    color: #eebebe;
                }

                // keyword.control.ternary.java.el
                .syntax--keyword.syntax--control.syntax--ternary.syntax--java.syntax--el {
                    color: #78c069;
                }
            }
        }

        // meta.tag.other.html
        .syntax--meta.syntax--tag.syntax--other.syntax--html {
            color: #dba36f;

            // entity.name.tag.other.html
            .syntax--entity.syntax--name.syntax--tag.syntax--other.syntax--html {
                color: #dba36f;
            }

            // meta.attribute-with-value.html
            .syntax--meta.syntax--attribute-with-value.syntax--html {
                // string.quoted.double.html
                .syntax--string.syntax--quoted.syntax--double.syntax--html {
                    color: #75c9d6;
                }

                // entity.other.attribute-name.html
                .syntax--entity.syntax--other.syntax--attribute-name.syntax--html {
                    color: #dba36f;
                }
            }
        }

        // meta.tag.script.html
        .syntax--meta.syntax--tag.syntax--script.syntax--html {
            color: #FFFFFF;

            // entity.name.tag.script.html
            .syntax--entity.syntax--name.syntax--tag.syntax--script.syntax--html {
                color: #dba36f;
            }

            // source.js.embedded.html
            .syntax--source.syntax--js.syntax--embedded.syntax--html {

                // meta.function-call.js
                .syntax--meta.syntax--function-call.syntax--js {

                    // entity.name.function.js
                    .syntax--entity.syntax--name.syntax--function.syntax--js {
                        color: #d6d458;
                    }

                    // meta.arguments.js
                    .syntax--meta.syntax--arguments.syntax--js {

                        // string.quoted.double.js
                        .syntax--string.syntax--quoted.syntax--double.syntax--js {
                            color: #75c9d6;
                        }

                        // string.quoted.single.js
                        .syntax--string.syntax--quoted.syntax--single.syntax--js {
                            color: #75c9d6;
                        }

                        // meta.function.js
                        .syntax--meta.syntax--function.syntax--js {
                            // storage.type.function.js
                            .syntax--storage.syntax--type.syntax--function.syntax--js {
                                color: #d4a5e3;
                            }
                        }

                        // keyword.control.js
                        .syntax--keyword.syntax--control.syntax--js {
                            color: #d4a5e3;
                        }
                    }
                }

                // meta.method-call.js
                .syntax--meta.syntax--method-call.syntax--js {

                    // meta.arguments.js
                    .syntax--meta.syntax--arguments.syntax--js {

                        // keyword.control.js
                        .syntax--keyword.syntax--control.syntax--js {
                            color: #d4a5e3;
                        }

                        // variable.language.js
                        .syntax--variable.syntax--language.syntax--js {
                            color: #d6d458;
                        }

                        // support.variable.dom.js
                        .syntax--support.syntax--variable.syntax--dom.syntax--js {
                            color: #d6d458;
                        }

                        // support.variable.property.dom.js
                        .syntax--support.syntax--variable.syntax--property.syntax--dom.syntax--js {
                            color: #d6d458;
                        }

                        // constant.numeric.decimal.js
                        .syntax--constant.syntax--numeric.syntax--decimal.syntax--js {
                            color: #eebebe;
                        }

                        // meta.brace.curly.js
                        .syntax--meta.syntax--brace.syntax--curly.syntax--js {
                            color: #FFFFFF;
                        }

                        // meta.brace.round.js
                        .syntax--meta.syntax--brace.syntax--round.syntax--js {
                            color: #FFFFFF;
                        }

                        // string.quoted.double.js
                        .syntax--string.syntax--quoted.syntax--double.syntax--js {
                            color: #75c9d6;

                            // meta.embedded.line.el_expression.jsp
                            .syntax--meta.syntax--embedded.syntax--line.syntax--el_expression.syntax--jsp {
                                // source.java
                                .syntax--source.syntax--java {
                                    color: #FFFFFF;

                                    // keyword.control.ternary.java.el
                                    .syntax--keyword.syntax--control.syntax--ternary.syntax--java.syntax--el {
                                        color: #d6d458;
                                    }
                                }

                                // punctuation.section.embedded.begin.jsp
                                .syntax--punctuation.syntax--section.syntax--embedded.syntax--begin.syntax--jsp {
                                    color: #dba36f;
                                }

                            }
                        }

                        // string.quoted.single.js
                        .syntax--string.syntax--quoted.syntax--single.syntax--js {
                            color: #75c9d6;
                        }

                        // meta.function.js
                        .syntax--meta.syntax--function.syntax--js {
                            // storage.type.function.js
                            .syntax--storage.syntax--type.syntax--function.syntax--js {
                                color: #d4a5e3;
                            }
                        }

                        // support.function.js
                        .syntax--support.syntax--function.syntax--js {
                            color: #d4a5e3;
                        }
                    }

                    // entity.name.function.js
                    .syntax--entity.syntax--name.syntax--function.syntax--js {
                        color: #d4a5e3;
                    }
                }
            }
        }

        // comment.block.html
        .syntax--comment.syntax--block.syntax--html {
            color: #aaaaaa;
        }
    }
}
```
