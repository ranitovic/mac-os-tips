# Customize Atom editor on Mac OS

#### Backup the original configuration
All customization can be done in ~/.atom/style.less file, so let's make a copy called ~/.atom/style-original.less


#### Syntax highlight, how to know which class is displayed

Put cursor in front of the PHP keyword, then Command + Alt + P to view classes,
use the last class in the style.less to customize the syntax color

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
```
