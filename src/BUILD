file(
    name="linux_aarch64_py311",
    source="linux_aarch64_py311.json"
)
file(
    name="linux_x86_64_py312",
    source="linux_x86_64_py312.json",
)

python_sources(
    name="src",
    sources=["*.py"],
)

pex_binary(
    name="pex",
    entry_point="__main__.py",
    complete_platforms=[":linux_aarch64_py311", ":linux_x86_64_py312"],
    execution_mode="venv",
    restartable=True,
    dependencies=[
        ":src",
    ],
)


