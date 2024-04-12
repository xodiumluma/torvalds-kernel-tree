# GPL-2.0

# rustdoc path
rustdoc_output := $(objtree)/Documentation/output/rust/rustdoc

obj-$(CONFIG_RUST) += core.o compiler_builtins.o
always-$(CONFIG_RUST) += exports_core_generated.h

# There are no headers/prototypes; helpers will have missing prototypes as they are exported only for Rust
obj-$(CONFIG_RUST) += helpers.o 
CFLAGS_REMOVE_helpers.o = -Wmissing-prototypes -Wmissing-declarations

always-$(CONFIG_RUST) += libmacros.so
no-clean-files += libmacros.so

always-$(CONFIG_RUST) += bindings/bindings_generated.rs bindings/bindings_helpers_generated.rs
obj-$(CONFIG_RUST) += alloc.o bindings.o kernel.o
always-$(CONFIG_RUST) += exports_alloc_generated.h exports_bindings_generated.h \
		exports_kernel_generated.h

always-$(CONFIG_RUST) += uapi/uapi_generated.rs
obj-$(CONFIG_RUST) += uapi.o