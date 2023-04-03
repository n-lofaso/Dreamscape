# Dreamscape
## Table of Contents

* [Description](#description)
* [Code Examples](#code-examples)
* [Important links](#important-links)
* [Languages Used](#languages-used)
* [Contributors](#contributers)

## Description

    Dreamscape is an application geared towards goal achievement. Using a combination of imagery and journaling, Dreamscapes aims to assist users with accountability and visualization. Visualization and journaling have always been indisposable keys for being successful in the persuit of goals, and with Dreamscape these tools are located on the same platform. 

    The main motivation behind the development of this applciation is simplification. While there are many platforms where users are able to use visualization and journaling techniques (i.e. Pinterest), there are very few that offer both of the techniques on the same platform. The ease of access Dreamscape offers increases the liklihood of regular use by users and increases the rate of goal completion. 

## Code Examples

Example of code used to create the Vision Board:

```js
function App() {
  const [query, setQuery] = useState('');
  const [photos, setPhotos] = useState([]);

  const handleSearch = useCallback(async () => {
    try {
      const response = await fetch(`/api/unsplash?query=${query}`);
      const data = await response.json();
      setPhotos(data);
    } catch (error) {
      console.error(error);
    }
  }, [query]);
```

Example of code used to create the Diary:
```js
function DiaryEntry({ entry, handleRemoveEntry }) {
  return (
    <div className='card bg-dark-subtle m-5' key={entry._id}>
      <div className='card-header'>{entry.title}</div>
      <div className='card-body'>
        <p className='card-text'>{entry.entry}</p>
        <button
          type='button'
          className='btn btn-danger'
          onClick={() => handleRemoveEntry(entry.entryID)}
        >
          Remove
        </button>
      </div>
    </div>
  );
}
```

## Important Links
[GitHub Repository](https://github.com/keekerr/Dreamscape)

[Deployed Application](http://dreamscape-vision-board.herokuapp.com/)

## Languages Used


## Contributors

Keeley Kerr - [GitHub](https://github.com/keekerr)

Josh Lemmond - [GitHub](https://github.com/Joshvuh)

Alyssa Maples - [Github](https://github.com/armaples)

Nick Lo Faso - [GitHub](https://github.com/n-lofaso)

Sarah Lang - [GitHub](https://github.com/sarahlang9800)

