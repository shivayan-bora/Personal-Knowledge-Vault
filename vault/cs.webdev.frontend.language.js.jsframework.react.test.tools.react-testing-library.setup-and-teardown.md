---
id: zy5dnn1on96dmwfbcrrdyz2
title: Setup and Teardown
desc: ''
updated: 1658986402806
created: 1658985840783
---

Similar to [[cs.webdev.frontend.language.js.testing.tools.jest.setup-teardown]].

```js
const MockFollowersList = () => {
    return (
        <BrowserRouter>
            <FollowersList />
        </BrowserRouter>
    )
}

describe('FollowersList', () => {
    // Used for initializations
    beforeEach(() => {
        console.log('Running Before Each Test')
    })

    beforeAll(() => {
        console.log('Running Once Before All Tests')
    })

    // Used for cleanups
    afterEach(() => {
        console.log('Running After Each Test')
    })

    afterAll(() => {
        console.log('Running Once After All Tests')
    })

    it('should render the followers list card', async () => {
        render(<MockFollowersList />)
        const followerDivElement = await screen.findByTestId('follower-item-0')
        expect(followerDivElement).toBeInTheDocument()
    })

    it('should render the followers list card 2', async () => {
        render(<MockFollowersList />)
        const followerDivElement = await screen.findByTestId('follower-item-0')
        expect(followerDivElement).toBeInTheDocument()
    })

    it('should render the followers list card 3', async () => {
        render(<MockFollowersList />)
        const followerDivElement = await screen.findByTestId('follower-item-0')
        expect(followerDivElement).toBeInTheDocument()
    })
})
```
