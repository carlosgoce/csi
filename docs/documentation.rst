Documentation
=============
It is just a spec testing tool with it's own naming conventions.

The idea it is to be able to create alias for everything and
chose the naming convention that you like.

Expected Functionality
----------------------


.. code:: python

    class ExampleScene(Scene):
        @subject()
        subject = some_object()

        # Subject should be also a method
        # @subject()
        # def subject(self):
        #    return some_object()

        def investigate_something_works(self):
            self.subject().should().be_true()

        # Nested scenes (contexts) should be possible
        class NestedScene(Scene):
            pass

    # Alternative

    import csi

    @csi.Scene()
    def it_should_be_true():
        csi.investigate(True).should().be(True)

        # Nested
        @csi.Scene()
        def it_can_nest_scenes():
            pass
