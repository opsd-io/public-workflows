# Changelog

## 1.0.0 (2026-09-16)


### Features

* add cli release bundles ([#9](https://github.com/opsd-io/public-workflows/issues/9)) ([48d4b6c](https://github.com/opsd-io/public-workflows/commit/48d4b6c82185a93dd69e142ac7bff772dc8422ff))
* add conventional commit validation workflow ([#38](https://github.com/opsd-io/public-workflows/issues/38)) ([9f783a8](https://github.com/opsd-io/public-workflows/commit/9f783a8988ffd425aceba77b5a7528bcd7fdcc20))
* add public infrastructure plan workflow ([#32](https://github.com/opsd-io/public-workflows/issues/32)) ([86e765c](https://github.com/opsd-io/public-workflows/commit/86e765c29d0c647c792693371ed542683a72f42c))
* add release automation ([0e2d2e9](https://github.com/opsd-io/public-workflows/commit/0e2d2e918cfa2669c6390ddcc2966b1fd68b5f70))
* add release automation ([a748212](https://github.com/opsd-io/public-workflows/commit/a7482122374193dca2cc4d460bca1a15c7a719ce))
* enable reusable workflow linting ([919a377](https://github.com/opsd-io/public-workflows/commit/919a377359a32bb31537808338b63e8ea4c75829))
* enable reusable workflow linting ([26d659f](https://github.com/opsd-io/public-workflows/commit/26d659f553e82f8238682547a4c5f8d18e76a5b9))
* generate public scenarios from capabilities ([#36](https://github.com/opsd-io/public-workflows/issues/36)) ([fc0ecc8](https://github.com/opsd-io/public-workflows/commit/fc0ecc8a508cc5c9090cafdc6f73afd0c5a0dd36))
* ignore ci-only release commits ([#15](https://github.com/opsd-io/public-workflows/issues/15)) ([a8fcd45](https://github.com/opsd-io/public-workflows/commit/a8fcd45e4487b2fa1e8f479b241bb1977307bece))
* include provider in public matrix ([#35](https://github.com/opsd-io/public-workflows/issues/35)) ([90e20de](https://github.com/opsd-io/public-workflows/commit/90e20de7914df1a4acfb4276f8a3ba23fd0fd4b9))
* run public plans from integration tests ([2be4e87](https://github.com/opsd-io/public-workflows/commit/2be4e87d2491a78e54a224f665b3376fb0cf9c3a))
* support automated source version bumps ([#22](https://github.com/opsd-io/public-workflows/issues/22)) ([f4cad00](https://github.com/opsd-io/public-workflows/commit/f4cad000277182422fcf41c506cd8181a4878473))
* test modules with Terraform and OpenTofu ([463eb38](https://github.com/opsd-io/public-workflows/commit/463eb388527dc51259e00359c07085cf90d5681a))
* test modules with Terraform and OpenTofu ([464a248](https://github.com/opsd-io/public-workflows/commit/464a248c465063aea1d153e683445e534527bb96))


### Bug Fixes

* **ci:** handle release please validation and baseline ([#42](https://github.com/opsd-io/public-workflows/issues/42)) ([096052f](https://github.com/opsd-io/public-workflows/commit/096052ffc7b53a95b6e147f46ec61353b6db1708))
* **ci:** resolve integration test compatibility path ([e925260](https://github.com/opsd-io/public-workflows/commit/e925260addd2d4c4ed87bae2b17e7256eec53dc3))
* configure global release version file ([#26](https://github.com/opsd-io/public-workflows/issues/26)) ([a0c20d9](https://github.com/opsd-io/public-workflows/commit/a0c20d9689bbc82daf19aaa5d3065162da7e9673))
* configure release package version file ([#24](https://github.com/opsd-io/public-workflows/issues/24)) ([ffb1add](https://github.com/opsd-io/public-workflows/commit/ffb1add18d025b40ef9f0c0f94efc03b7ff5854e))
* configure release please version file ([#23](https://github.com/opsd-io/public-workflows/issues/23)) ([9c2ca49](https://github.com/opsd-io/public-workflows/commit/9c2ca49958e70315ca7054fd184a5fd623d13e8d))
* force initial release version ([#31](https://github.com/opsd-io/public-workflows/issues/31)) ([7fa39b0](https://github.com/opsd-io/public-workflows/commit/7fa39b0aef9edf41de5d14e48c6d388751160bdf))
* initialize release version ([#30](https://github.com/opsd-io/public-workflows/issues/30)) ([244ff5f](https://github.com/opsd-io/public-workflows/commit/244ff5f89bd9c342c2a0df9eb8380015adafe577))
* install ruby from ruby version file ([#16](https://github.com/opsd-io/public-workflows/issues/16)) ([20a37b8](https://github.com/opsd-io/public-workflows/commit/20a37b88683c22b241d43accd85201d939ac99c8))
* pass release version to Release Please ([#37](https://github.com/opsd-io/public-workflows/issues/37)) ([8a2dbfa](https://github.com/opsd-io/public-workflows/commit/8a2dbfac6c1718f5f9acdd53478f73bc4744df65))
* pin checkout to v6.0.3 ([#11](https://github.com/opsd-io/public-workflows/issues/11)) ([416538b](https://github.com/opsd-io/public-workflows/commit/416538b488ccc77554250fbedc36b84530071175))
* pin valid checkout commit ([#33](https://github.com/opsd-io/public-workflows/issues/33)) ([0e33d52](https://github.com/opsd-io/public-workflows/commit/0e33d52f347490c5a869c112b48b171645d93234))
* publish cli release assets ([#10](https://github.com/opsd-io/public-workflows/issues/10)) ([8c87a46](https://github.com/opsd-io/public-workflows/commit/8c87a46f93ad57f1e0a92c0e01a44c05f1d2f7b9))
* read release version from PR title ([#29](https://github.com/opsd-io/public-workflows/issues/29)) ([57c0b06](https://github.com/opsd-io/public-workflows/commit/57c0b069bfae591483a54fd7938942f72550abd7))
* reuse compatible runner ruby installations ([#17](https://github.com/opsd-io/public-workflows/issues/17)) ([331a3ab](https://github.com/opsd-io/public-workflows/commit/331a3abd9a07e6771792b4f4c4a832d4c7a3c501))
* set release component for Ruby projects ([#27](https://github.com/opsd-io/public-workflows/issues/27)) ([24c5d26](https://github.com/opsd-io/public-workflows/commit/24c5d26e884c4a8efe6adeac8e19c6a53374b552))
* set release strategy per package ([#25](https://github.com/opsd-io/public-workflows/issues/25)) ([3789392](https://github.com/opsd-io/public-workflows/commit/3789392344f5596e42babcb6f835bc1a0082441d))
* support Ruby builds on macOS 26 ([#20](https://github.com/opsd-io/public-workflows/issues/20)) ([937936d](https://github.com/opsd-io/public-workflows/commit/937936dee579f970f4fedd32102a3e8ea7036251))
* support self-hosted ruby setup ([#12](https://github.com/opsd-io/public-workflows/issues/12)) ([3873caf](https://github.com/opsd-io/public-workflows/commit/3873caf4472fb51d51b37e9d69a57a05f5f85da5))
* target caller repository for release assets ([#19](https://github.com/opsd-io/public-workflows/issues/19)) ([1737140](https://github.com/opsd-io/public-workflows/commit/173714013a83d1c861e91d47bc14e9f88d00b1bd))
* update release source version ([#28](https://github.com/opsd-io/public-workflows/issues/28)) ([d81b78d](https://github.com/opsd-io/public-workflows/commit/d81b78d5f16afe71450b567ccca34b9c6e256d43))
* update Ruby setup action ([#34](https://github.com/opsd-io/public-workflows/issues/34)) ([4cc96e4](https://github.com/opsd-io/public-workflows/commit/4cc96e47425603e062476ab44127160c5c7d2b4a))
* use rbenv ruby build plugin ([#18](https://github.com/opsd-io/public-workflows/issues/18)) ([62fef0c](https://github.com/opsd-io/public-workflows/commit/62fef0cd1a05aa116ab0c983baea89e6fadc9c00))
* use runner ruby for cli bundles ([#13](https://github.com/opsd-io/public-workflows/issues/13)) ([a31ce3f](https://github.com/opsd-io/public-workflows/commit/a31ce3f426718f83ae0ad2f36cfad48d7ff9e8d5))
