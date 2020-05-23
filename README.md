# Snippets
Snippets config files to improve my development flow. The snippets are basically for my own needs and programming style. But I hope that they can help in your work flow.

## Files
|File   |Description   |
|---|---|
|javascript.json   |Snippets for JavaScript focused in React development   |

## Usage
Type the prefix, select the respective in the menu, custom with your code and press TAB or ENTER to jump between fields.

### How to install
- 1st option

  Go to File > Preferences > User Snippets, selection the language to set the snippets. The snippets file is an JSON file with the name of the language (ex: javascript.json). Then, copy the content from the repectivelly file in this repository, to your file in VS Code.
  
- 2st option

  Find the snippet folder of VS Code. In my computer was: Users > umbutech > Library > Application Support > Code > snippets

### Examples

#### React functional component with hooks
- Prefix
````
rnfhooks
````

- Body
`````
import React, {useState, useEffect} from 'react';
import {Container} from './styles.js';

function func() {
  const [estado, modificador] = useState();

  useEffect(() => {
  }, []);

  return <Container />;

export default func;
`````

#### Request data function
- Prefix
`````
rnreq
`````

- Body
`````
async function func() {
  setLoading(true);
  const result = await Service.function();
  console.log(result);
  if (result.ok) {
    setData(result.data);
  } else {
    setError();
  }
  setLoading(false);
}
`````

#### Default FlatList
- Prefix
`````
flatlist
`````

- Body
`````
<FlatList
  data={data}
  keyExtractor={item => String(item.id)}
  renderItem={_renderItem}
  ListEmptyComponent={component}
/>
`````

#### Service static function
- Prefix
```
servFunc
```

- Body
```
static async func(data) {
  return api
    .post(`/route/`, {params: {...data}})
    .then(async (response) => {
      if (response.status) {
        return {
          data: response.data,
          ok: true,
        };
      }
      return {
        ok: false,
        message: response.data.message || 'Erro',
      };
    })
    .catch(error => ({
       ok: false,
       message: error.response.data.message || 'Erro',
    }));
}
```

### Redux map constants
- Prefix
```
mapProps
```

- Body
```
const mapStateToProps = state => ({
  state: state.reducer,
});

const mapDispatchToProps = {
  function: Creators.action,
};
```

#### Proptypes objects
- Prefix
```
proptypes
```

- Body
```
func.defaultProps = {
  prop: null,
};

func.propTypes = {
  prop: PropTypes.type,
};
```
