# Bash Challenges

## Setup

Follow the instructions here: https://exercism.org/docs/tracks/bash/tests

### Dependencies
Wrapper function in bashrc (zshrc in my case)
`
exercism () {
    local out
    readarray -t out < <(command exercism "$@")
    printf '%s\n' "${out[@]}"
    if [[ $1 == "download" && -d "${out[-1]}" ]]; then
        cd "${out[-1]}" || return 1
    fi
}
`

bats-core


