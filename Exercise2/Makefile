

# This Makefile was automatically generated. Please do not make any changes
# here.

# To test if your solution still has all the right types and uses Safe
# Haskell, run `make`. 

TYPECHECK = Exercise_typecheck.hs

TEMPDIR := $(shell mktemp -udt fp-typecheck-XXXX)

COMMAND = runghc $(TYPECHECK)

default: typecheck tests

typecheck: $(TYPECHECK) integrity Exercise.hs

	@# Create temporary directory
	@mkdir $(TEMPDIR)

	@echo \* Type checking Exercise.hs...
	@echo
	@cp Exercise.hs $(TEMPDIR)
	@cp $(TYPECHECK) $(TEMPDIR)
	@echo "$(COMMAND)"
	@cd $(TEMPDIR) && $(COMMAND) \
	 || (echo "* Failed to type check your Exercise.hs."; \
	     rm -rf $(TEMPDIR); \
	     false)

	@echo ""
	@echo "* Your Exercise.hs compiled successfully, you did not change any"
	@echo "  types, and use only the safe subset of Haskell. You can now submit."
	@echo ""

	@# Clean up.
	@rm -rf $(TEMPDIR)

tests: 
	@echo "  I will now run your solution with some inputs, so you get an"
	@echo "  indication of the mark you might get."
	@echo ""
	runhaskell TestBench

integrity:
	@test "20659fd646dedaea59e3112da14aef9c3efc6e18  $(TYPECHECK)" \
        == "$(shell sha1sum $(TYPECHECK))" \
	|| ( echo "Error: somebody changed $(TYPECHECK)."; \
	     echo "The results of the pre-submit check might be wrong."; \
	     echo "Please re-download $(TYPECHECK) from the web site."; \
	     false )


.PHONY: typecheck tests integrity
