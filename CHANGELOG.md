# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.2.2]

- Fix bug in pip install of v0.2.1 due to scikit-build-core removing all `.metal` files in the source distribution (see #701)

## [0.2.1]

- Fix bug in pip install of v0.2.0 due to .git folder being included in the source distribution (see #701)

## [0.2.0]

- Migrated to scikit-build-core build system by @abetlen in #499
- Use `numpy` views for `LogitsProcessor` and `StoppingCriteria` instead of python lists by @abetlen in #499
- Drop support for end-of-life Python3.7 by @abetlen in #499
- Convert low level `llama.cpp` constants to use basic python types instead of `ctypes` types by @abetlen in #499

## [0.1.85]

- Add `llama_cpp.__version__` attribute by @janvdp in #684
- Fix low level api examples by @jbochi in #680

## [0.1.84]

- Update llama.cpp

## [0.1.83]

- Update llama.cpp

## [0.1.82]

- Update llama.cpp

## [0.1.81]

- Update llama.cpp

## [0.1.80]

- Update llama.cpp

## [0.1.79]

- GGUF Support (breaking change requiring new model format)

## [0.1.78]

- Grammar based sampling via LlamaGrammar which can be passed to completions
- Make n_gpu_layers == -1 offload all layers

## [0.1.77]

- (llama.cpp) Update llama.cpp add support for LLaMa 2 70B
- (server) Add temporary n_gqa and rms_norm_eps parameters required for LLaMa 2 70B

## [0.1.76]

- (llama.cpp) Update llama.cpp add support for LLaMa 2 70B

## [0.1.75]

- Update llama.cpp

## [0.1.74]

- (server) OpenAI style error responses

## [0.1.73]

- (server) Add rope parameters to server settings

## [0.1.72]

- (llama.cpp) Update llama.cpp added custom_rope for extended context lengths

## [0.1.71]

- (llama.cpp) Update llama.cpp

- (server) Fix several pydantic v2 migration bugs

## [0.1.70]

- (Llama.create_completion) Revert change so that `max_tokens` is not truncated to `context_size` in `create_completion`
- (server) Fixed changed settings field names from pydantic v2 migration

## [0.1.69]

- (server) Streaming requests can are now interrupted pre-maturely when a concurrent request is made. Can be controlled with the `interrupt_requests` setting.
- (server) Moved to fastapi v0.100.0 and pydantic v2
- (docker) Added a new "simple" image that builds llama.cpp from source when started.
- (server) performance improvements by avoiding unnecessary memory allocations during sampling

## [0.1.68]

- (llama.cpp) Update llama.cpp

## [0.1.67]

- Fix performance bug in Llama model by pre-allocating memory tokens and logits.
- Fix bug in Llama model where the model was not free'd after use.

## [0.1.66]

- (llama.cpp) New model API

- Performance issue during eval caused by looped np.concatenate call
- State pickling issue when saving cache to disk

## [0.1.65]

- (llama.cpp) Fix struct misalignment bug

## [0.1.64]

- (llama.cpp) Update llama.cpp
- Fix docs for seed. Set -1 for random.

## [0.1.63]

- (llama.cpp) Add full gpu utilisation in CUDA
- (llama.cpp) Add get_vocab
- (llama.cpp) Add low_vram parameter
- (server) Add logit_bias parameter

## [0.1.62]

- Metal support working
- Cache re-enabled

## [0.1.61]

- Fix broken pip installation

## [0.1.60]

NOTE: This release was deleted due to a bug  with the packaging system that caused pip installations to fail.

- Truncate max_tokens in create_completion so requested tokens doesn't exceed context size.
- Temporarily disable cache for completion requests

## [v0.1.59]

- (llama.cpp) k-quants support
- (server) mirostat sampling parameters to server
- Support both `.so` and `.dylib` for `libllama` on MacOS

## [v0.1.58]

- (llama.cpp) Metal Silicon support

## [v0.1.57]

- (llama.cpp) OpenLlama 3B support

## [v0.1.56]

- (misc) Added first version of the changelog
- (server) Use async routes
- (python-api) Use numpy for internal buffers to reduce memory usage and improve performance.
- (python-api) Performance bug in stop sequence check slowing down streaming.