### file

- 유형의 [\<input\>](https://developer.mozilla.org/ko/docs/Web/HTML/Element/input) 요소에는 저장 장치의 파일을 하나 혹은 여러 개 선택할 수 있습니다. 그 후, [양식을 제출](https://developer.mozilla.org/ko/docs/Learn/HTML/Forms)해 서버로 전송하거나, [File API](https://developer.mozilla.org/ko/docs/Web/API/File/Using_files_from_web_applications)를 사용한 JavaScript 코드로 조작할 수 있습니다.

- [mozilla](https://developer.mozilla.org/ko/docs/Web/HTML/Element/Input/file
- file filter
  `<input accept="file_extension|audio/*|video/*|image/*|media_type">`

  - [w3schools](https://www.w3schools.com/tags/att_input_accept.asp)

    #### code

    ```
        const onchange = (e: React.FormEvent) => {
            e.stopPropagation()
            e.preventDefault()

            const files: FileList | null = (e.target as HTMLInputElement).files

            if (files === null) return

            var reader = new FileReader()

            reader.onload = function (e) {
                if (e.target) {
                    e.target.result
                }
            }

            reader.readAsDataURL(files[0])
        }

        const clearInput = (e: React.MouseEvent) => {
            ;(e.target as HTMLInputElement).value = ''
        }

        return (
            <input
                type="file"
                accept="image/*"
                onChange={e => onchange(e)}
                onClick={e => clearInput(e)}
            />
        )
    ```

    ### test with react testing library

    ```
        import React from 'react'
        import {render, fireEvent, wait} from '@testing-library/react'
        import {Provider} from 'react-redux'

        it('input file change', async () => {
            const {container:any} = render(<Provider store={store}><Component /></Provider>)

            const file = new File(['123'], 'test.png', {type: 'image/png'})
            fireEvent.change(container.querySelector(`input[type=file]`), {target: {files: [file], result: ''}})

            // wait
            await wait(() => container.querySelector(`img`).getAttribute('src') !== '')

            expect(container.querySelector(`img`)).not.toHaveAttribute('src', '')
        })
    ```
