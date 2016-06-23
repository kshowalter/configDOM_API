# configDOM API

## Example

    {
      type: 'div'
      children: [
        {
          tag: 'span',
          text: 'hello world'
        }
      ]
    }

    becomes:
    <div>
      <span>hello world</span>
    </div>



## API for passed configuration object:

### tag / type
HTML tag name

Example:
    {
      tag: 'div'
    }

    becomes:
    <div></div>

### props
This contains the element properties

Example:
    {
      tag: 'div'
      props: {
        className: 'test'
      }
    }

    becomes:
    <div className="test"></div>



### text
This sets the text content. Also works to insert raw HTML.

Example:
    {
      tag: 'span',
      text: 'hello world'
    }

    becomes:
    <span>hello world</span>

    // TODO: confirm this will override children and append if placed in config object after them.

### children

Accepts:
* configDOM object: appends sub-configDOM
* String: creates and appends a text node
* DOM object: appends the raw object
  * child.constructor.prototype === HTMLElement
  * child instanceof SVGElement
