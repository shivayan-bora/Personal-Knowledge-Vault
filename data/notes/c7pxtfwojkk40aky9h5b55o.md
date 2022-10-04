

![Problem with async requests in tests](/assets/images/2022-07-28-09-58-57.png)

To test async operations, we face the following problems:

1. Requests cost money either to us or the provider of the API.
2. Requests can be slow depending on the API.
3. Our tests are dependent on something that's external.

To fix this, we can mock our API requests so that we are not dependent on an external source.

For mocking, we do the following.

1. In this example, we would be mocking axios. Firstly, we need to create a folder called `__mocks__`.
2. Then we create a file called axios.js. **Please note that the name of the file and the folder is very important.**

```js
const mockResponse = {
    data: {
        results: [
            {
                name: {
                    first: "Laith",
                    last: "Harb"
                },
                picture: {
                    large: "https://randomuser.me/api/portraits/men/59.jpg"
                },
                login: {
                    username: "ThePhonyGOAT"
                }
            }
        ]
    }
}


export default {
    get: jest.fn().mockResolvedValue(mockResponse)
}
```

`jest.fn()` is used to create mock functions.

For capturing elements dependent on an async API call, we need to use `findBy` as follows:

```js
const MockFollowersList = () => {
    return (
        <BrowserRouter>
            <FollowersList />
        </BrowserRouter>
    )
}

describe('FollowersList', () => {

    it('should render the followers list card', async () => {
        render(<MockFollowersList />)
        const followerDivElement = await screen.findByTestId('follower-item-0')
        expect(followerDivElement).toBeInTheDocument()
    })
})
```

Still here it won't work as React Scripts reset our mocks on every render. To make sure this doesn't happen, there's a way to test:

1. Go to the path: `node_modules/react-scripts/scripts/utils/createJestConfig.js`.
2. Search for the `resetMocks` which would be set to `true`. It's usually in a `config` object and on line 69.
3. Set it's value to `false` and restart your test runner.

Although this method isn't recommended and we need to find an alternative or check if it's fixed. #todo
